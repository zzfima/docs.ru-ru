---
title: Учетные данные канала — gRPC для разработчиков WCF
description: Как реализовать и использовать учетные данные канала gRPC в ASP.NET Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61141dc4143f36f9ac511c3369c3fde668c9d703
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841669"
---
# <a name="channel-credentials"></a>Учетные данные канала

Как следует из названия, учетные данные канала присоединяются к базовому каналу gRPC. Стандартная форма учетных данных канала использует проверку подлинности на основе сертификата клиента, где клиент предоставляет TLS-сертификат при установлении соединения, который проверяется сервером перед тем, как разрешить любые вызовы.

Учетные данные канала можно сочетать с учетными данными вызова для обеспечения полной безопасности службы gRPC. Учетные данные канала подтверждают, что клиентскому приложению разрешен доступ к службе, а учетные данные вызова предоставляют сведения о пользователе, использующем клиентское приложение.

Проверка подлинности сертификата клиента работает для gRPC так же, как и для ASP.NET Core. Процесс настройки будет показан здесь, но дополнительные сведения можно найти в статье [Настройка проверки подлинности сертификата в ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .

В целях разработки можно использовать самозаверяющий сертификат, но для рабочей среды следует использовать правильный HTTPS-сертификат, подписанный доверенным центром сертификации.

## <a name="adding-certificate-authentication-to-the-server"></a>Добавление проверки подлинности на сертификат на сервер

Необходимо настроить проверку подлинности с помощью сертификата на уровне узла, например на сервере Kestrel и в конвейере ASP.NET Core.

### <a name="configuring-certificate-validation-on-kestrel"></a>Настройка проверки сертификата в Kestrel

Можно настроить Kestrel (HTTP-сервер ASP.NET Core), чтобы требовать сертификат клиента, и при необходимости выполнить некоторую проверку предоставляемого сертификата перед принятием входящих подключений. Эта конфигурация выполняется в методе `CreateWebHostBuilder` класса `Program`, а не в `Startup`.

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

Параметр `ClientCertificateMode.RequireCertificate` приведет к тому, что Kestrel немедленно отклонит любой запрос на подключение, который не предоставляет сертификат клиента, но сертификат не будет проверен. Добавление обратного вызова `ClientCertificateValidation` позволяет Kestrel проверить сертификат клиента (в данном случае убедиться, что он был выдан тем же *центром сертификации* , что и сертификат сервера) в момент, когда соединение установлено, до того, как будет запущен конвейер ASP.NET Core.

### <a name="adding-aspnet-core-certificate-authentication"></a>Добавление ASP.NET Core проверки подлинности сертификата

Проверка подлинности сертификата обеспечивается пакетом NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) .

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

## <a name="providing-channel-credentials-in-the-client-application"></a>Предоставление учетных данных канала в клиентском приложении

При использовании пакета `Grpc.Net.Client` сертификаты настраиваются на экземпляре <xref:System.Net.Http.HttpClient>, который предоставляется `GrpcChannel`, используемому для соединения.

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

## <a name="combining-channelcredentials-and-callcredentials"></a>Объединение Чаннелкредентиалс и Каллкредентиалс

Вы можете настроить сервер на использование проверки подлинности сертификата и маркера, применив изменения сертификата к серверу Kestrel и используя по промежуточного слоя JWT Bearer в ASP.NET Core.

Чтобы предоставить Чаннелкредентиалс и Каллкредентиалс на клиенте, используйте метод `ChannelCredentials.Create`, чтобы применить учетные данные вызова. Проверку подлинности на основе сертификата по-прежнему необходимо применять с помощью экземпляра <xref:System.Net.Http.HttpClient>: Если аргументы передаются в конструктор `SslCredentials`, внутренний код клиента создает исключение. Параметр `SslCredentials` включается в метод `Create` пакета `Grpc.Net.Client`, чтобы обеспечить совместимость с пакетом `Grpc.Core`.

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
> Вы можете использовать метод `ChannelCredentials.Create` для клиента без проверки подлинности на сертификате, чтобы передать учетные данные маркера при каждом вызове, сделанном в канале.

Версия [примера приложения Фуллстокктиккер gRPC с проверкой подлинности с помощью сертификата](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) находится на сайте GitHub.

>[!div class="step-by-step"]
>[Назад](call-credentials.md)
>[Вперед](encryption.md)
