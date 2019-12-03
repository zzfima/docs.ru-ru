---
title: Учетные данные канала — gRPC для разработчиков WCF
description: Как реализовать и использовать учетные данные канала gRPC в ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711489"
---
# <a name="channel-credentials"></a>Учетные данные канала

Как следует из названия, учетные данные канала присоединяются к базовому каналу gRPC. Стандартная форма учетных данных канала использует проверку подлинности на основе сертификата клиента. В этом процессе клиент предоставляет сертификат TLS, когда он создает соединение, а затем сервер проверяет это, прежде чем разрешить выполнение любых вызовов.

Учетные данные канала можно объединить с учетными данными вызова для обеспечения полной безопасности службы gRPC. Учетные данные канала подтверждают, что клиентскому приложению разрешен доступ к службе, а учетные данные вызова предоставляют сведения о пользователе, который использует клиентское приложение.

Проверка подлинности сертификата клиента работает для gRPC так же, как и для ASP.NET Core. Дополнительные сведения см. [в разделе Настройка проверки подлинности сертификата в ASP.NET Core](/aspnet/core/security/authentication/certauth).

В целях разработки можно использовать самозаверяющий сертификат, но для рабочей среды следует использовать правильный HTTPS-сертификат, подписанный доверенным центром сертификации.

## <a name="add-certificate-authentication-to-the-server"></a>Добавление проверки подлинности на сертификат на сервер

Настройте проверку подлинности на сертификате на уровне узла (например, на сервере Kestrel) и в конвейере ASP.NET Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Настройка проверки сертификата в Kestrel

Можно настроить Kestrel (HTTP-сервер ASP.NET Core), чтобы требовать сертификат клиента, и при необходимости выполнить некоторую проверку предоставляемого сертификата перед приемом входящих подключений. Это делается в методе `CreateWebHostBuilder` класса `Program`, а не в `Startup`.

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

Параметр `ClientCertificateMode.RequireCertificate` заставляет Kestrel немедленно отклонять любой запрос на подключение, который не предоставляет сертификат клиента, но этот параметр сам по себе не проверяет предоставленный сертификат. Добавьте обратный вызов `ClientCertificateValidation`, чтобы включить Kestrel для проверки сертификата клиента в момент подключения, до того, как будет выполнен конвейер ASP.NET Core. (В этом случае обратный вызов гарантирует, что он был выдан тем же *центром сертификации* , что и сертификат сервера.) 

### <a name="add-aspnet-core-certificate-authentication"></a>Добавление ASP.NET Core проверки подлинности сертификата

Пакет NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) обеспечивает проверку подлинности сертификата.

Добавьте службу проверки подлинности сертификата в метод `ConfigureServices` и добавьте проверку подлинности и авторизацию в конвейер ASP.NET Core в методе `Configure`.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Указание учетных данных канала в клиентском приложении

С помощью пакета `Grpc.Net.Client` вы настраиваете сертификаты на экземпляре <xref:System.Net.Http.HttpClient>, который предоставляется `GrpcChannel`, используемому для подключения.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Объединение Чаннелкредентиалс и Каллкредентиалс

Вы можете настроить сервер для использования проверки подлинности сертификата и маркера. Для этого примените изменения сертификата к серверу Kestrel и используйте по промежуточного слоя JWT Bearer в ASP.NET Core.

Чтобы предоставить `ChannelCredentials` и `CallCredentials` на клиенте, используйте метод `ChannelCredentials.Create` для применения учетных данных вызова. Вам по-прежнему необходимо применить проверку подлинности с помощью сертификата, используя экземпляр <xref:System.Net.Http.HttpClient>. При передаче аргументов в конструктор `SslCredentials` внутренний клиентский код создает исключение. Параметр `SslCredentials` включается в метод `Create` пакета `Grpc.Net.Client`, чтобы обеспечить совместимость с пакетом `Grpc.Core`.

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
> Для клиента можно использовать метод `ChannelCredentials.Create` без проверки подлинности на сертификате. Это удобный способ передачи учетных данных маркера при каждом вызове, сделанном в канале.

Версия [примера приложения Фуллстокктиккер gRPC с проверкой подлинности с помощью сертификата](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) находится на сайте GitHub.

>[!div class="step-by-step"]
>[Назад](call-credentials.md)
>[Вперед](encryption.md)
