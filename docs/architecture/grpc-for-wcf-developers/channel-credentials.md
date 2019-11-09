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
# <a name="channel-credentials"></a><span data-ttu-id="0f5d0-103">Учетные данные канала</span><span class="sxs-lookup"><span data-stu-id="0f5d0-103">Channel credentials</span></span>

<span data-ttu-id="0f5d0-104">Как следует из названия, учетные данные канала присоединяются к базовому каналу gRPC.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="0f5d0-105">Стандартная форма учетных данных канала использует проверку подлинности на основе сертификата клиента, где клиент предоставляет TLS-сертификат при установлении соединения, который проверяется сервером перед тем, как разрешить любые вызовы.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="0f5d0-106">Учетные данные канала можно сочетать с учетными данными вызова для обеспечения полной безопасности службы gRPC.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="0f5d0-107">Учетные данные канала подтверждают, что клиентскому приложению разрешен доступ к службе, а учетные данные вызова предоставляют сведения о пользователе, использующем клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="0f5d0-108">Проверка подлинности сертификата клиента работает для gRPC так же, как и для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="0f5d0-109">Процесс настройки будет показан здесь, но дополнительные сведения можно найти в статье [Настройка проверки подлинности сертификата в ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="0f5d0-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="0f5d0-110">В целях разработки можно использовать самозаверяющий сертификат, но для рабочей среды следует использовать правильный HTTPS-сертификат, подписанный доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="0f5d0-111">Добавление проверки подлинности на сертификат на сервер</span><span class="sxs-lookup"><span data-stu-id="0f5d0-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="0f5d0-112">Необходимо настроить проверку подлинности с помощью сертификата на уровне узла, например на сервере Kestrel и в конвейере ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="0f5d0-113">Настройка проверки сертификата в Kestrel</span><span class="sxs-lookup"><span data-stu-id="0f5d0-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="0f5d0-114">Можно настроить Kestrel (HTTP-сервер ASP.NET Core), чтобы требовать сертификат клиента, и при необходимости выполнить некоторую проверку предоставляемого сертификата перед принятием входящих подключений.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="0f5d0-115">Эта конфигурация выполняется в методе `CreateWebHostBuilder` класса `Program`, а не в `Startup`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="0f5d0-116">Параметр `ClientCertificateMode.RequireCertificate` приведет к тому, что Kestrel немедленно отклонит любой запрос на подключение, который не предоставляет сертификат клиента, но сертификат не будет проверен.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="0f5d0-117">Добавление обратного вызова `ClientCertificateValidation` позволяет Kestrel проверить сертификат клиента (в данном случае убедиться, что он был выдан тем же *центром сертификации* , что и сертификат сервера) в момент, когда соединение установлено, до того, как будет запущен конвейер ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="0f5d0-118">Добавление ASP.NET Core проверки подлинности сертификата</span><span class="sxs-lookup"><span data-stu-id="0f5d0-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="0f5d0-119">Проверка подлинности сертификата обеспечивается пакетом NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) .</span><span class="sxs-lookup"><span data-stu-id="0f5d0-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="0f5d0-120">Добавьте службу проверки подлинности сертификата в метод `ConfigureServices` и добавьте проверку подлинности и авторизацию в конвейер ASP.NET Core в методе `Configure`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="0f5d0-121">Предоставление учетных данных канала в клиентском приложении</span><span class="sxs-lookup"><span data-stu-id="0f5d0-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="0f5d0-122">При использовании пакета `Grpc.Net.Client` сертификаты настраиваются на экземпляре <xref:System.Net.Http.HttpClient>, который предоставляется `GrpcChannel`, используемому для соединения.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="0f5d0-123">Объединение Чаннелкредентиалс и Каллкредентиалс</span><span class="sxs-lookup"><span data-stu-id="0f5d0-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="0f5d0-124">Вы можете настроить сервер на использование проверки подлинности сертификата и маркера, применив изменения сертификата к серверу Kestrel и используя по промежуточного слоя JWT Bearer в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="0f5d0-125">Чтобы предоставить Чаннелкредентиалс и Каллкредентиалс на клиенте, используйте метод `ChannelCredentials.Create`, чтобы применить учетные данные вызова.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="0f5d0-126">Проверку подлинности на основе сертификата по-прежнему необходимо применять с помощью экземпляра <xref:System.Net.Http.HttpClient>: Если аргументы передаются в конструктор `SslCredentials`, внутренний код клиента создает исключение.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="0f5d0-127">Параметр `SslCredentials` включается в метод `Create` пакета `Grpc.Net.Client`, чтобы обеспечить совместимость с пакетом `Grpc.Core`.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="0f5d0-128">Вы можете использовать метод `ChannelCredentials.Create` для клиента без проверки подлинности на сертификате, чтобы передать учетные данные маркера при каждом вызове, сделанном в канале.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="0f5d0-129">Версия [примера приложения Фуллстокктиккер gRPC с проверкой подлинности с помощью сертификата](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) находится на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="0f5d0-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0f5d0-130">[Назад](call-credentials.md)
>[Вперед](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="0f5d0-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
