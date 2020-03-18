---
title: Учетные данные канала - gRPC для разработчиков WCF
description: Как реализовать и использовать учетные данные канала gRPC в ASP.NET Core 3.0.
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148209"
---
# <a name="channel-credentials"></a>Учетные данные канала

Как следует из названия, учетные данные канала прикрепляются к базовому каналу gRPC. Стандартная форма учетных данных канала использует аутентификацию сертификата клиента. В этом процессе клиент предоставляет сертификат TLS при подключении, а затем сервер проверяет это, прежде чем разрешить любые звонки.

Вы можете объединить учетные данные канала с учетными данными вызова, чтобы обеспечить полную безопасность для службы gRPC. Учетные данные канала доказывают, что клиентское приложение имеет доступ к службе, а учетные данные вызова предоставляют информацию о человеке, который использует клиентское приложение.

Проверка подлинности сертификата клиента работает для gRPC так же, как она работает для ASP.NET Core. Для получения дополнительной информации смотрите [проверку подлинности сертификата Настройка в ASP.NET Core](/aspnet/core/security/authentication/certauth).

Для целей разработки можно использовать сертификат, подписанный самостоятельно, но для производства следует использовать соответствующий сертификат HTTPS, подписанный доверенным органом.

## <a name="add-certificate-authentication-to-the-server"></a>Добавление проверки подлинности сертификата на сервер

Настройка аутентификации сертификата как на уровне хоста (например, на сервере Kestrel), так и в ASP.NET конвейера Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Настройка сертификата на Kestrel

Вы можете настроить Kestrel (ASP.NET core HTTP сервер), чтобы требовать сертификат клиента, и по желанию провести некоторую проверку поставляемого сертификата, прежде чем принимать входящие соединения. Вы делаете это `CreateWebHostBuilder` в `Program` методе класса, `Startup`а не в .

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

Настройка `ClientCertificateMode.RequireCertificate` заставляет Kestrel немедленно отклонить любой запрос на подключение, который не предоставляет сертификат клиента, но эта настройка сама по себе не будет проверять предоставленный сертификат. До `ClientCertificateValidation` подключения обратного вызова, чтобы Kestrel проверил сертификат клиента в момент подключения, до того, как будет включен конвейер ASP.NET Core. (В этом случае обратный вызов гарантирует, что он был выдан тем же *органом сертификата,* что и сертификат сервера.)

### <a name="add-aspnet-core-certificate-authentication"></a>Добавьте аутентификацию сертификата ASP.NET core

Пакет [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet обеспечивает аутентификацию сертификата.

Добавьте службу аутентификации сертификатов в `ConfigureServices` метод и добавьте `Configure` аутентификацию и авторизацию в ASP.NET ядро конвейера в методе.

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="provide-channel-credentials-in-the-client-application"></a>Предоставление учетных данных канала в клиентском приложении

С `Grpc.Net.Client` помощью пакета вы настраиваете сертификаты <xref:System.Net.Http.HttpClient> на `GrpcChannel` экземпляр, который предоставляется используемому для соединения.

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combine-channelcredentials-and-callcredentials"></a>Объедините ChannelCredentials и CallCredentials

Вы можете настроить сервер для использования как сертификата, так и проверки подлинности маркеров. Сделайте это, применяя изменения сертификата на серверЕ Kestrel и используя промежуточное программное обеспечение jWT в ASP.NET Core.

Чтобы предоставить как `ChannelCredentials` клиента, так и `CallCredentials` клиента, используйте `ChannelCredentials.Create` метод для применения учетных данных вызова. Вам все еще нужно применить проверку подлинности сертификата с помощью экземпляра. <xref:System.Net.Http.HttpClient> Если вы передаете какие-либо аргументы конструктору, `SslCredentials` внутренний код клиента бросает исключение. Параметр `SslCredentials` включен только `Grpc.Net.Client` в `Create` метод пакета для поддержания `Grpc.Core` совместимости с пакетом.

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> Вы можете `ChannelCredentials.Create` использовать метод для клиента без проверки подлинности сертификата. Это полезный способ передачи учетных данных маркеров с каждым вызовом, сделанным на канале.

Версия приложения [FullStockTicker образца gRPC с добавленной сертификатом подлинности](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) находится на GitHub.

>[!div class="step-by-step"]
>[Предыдущий](call-credentials.md)
>[Следующий](encryption.md)
