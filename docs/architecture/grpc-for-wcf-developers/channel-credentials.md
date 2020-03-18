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
# <a name="channel-credentials"></a><span data-ttu-id="429ba-103">Учетные данные канала</span><span class="sxs-lookup"><span data-stu-id="429ba-103">Channel credentials</span></span>

<span data-ttu-id="429ba-104">Как следует из названия, учетные данные канала прикрепляются к базовому каналу gRPC.</span><span class="sxs-lookup"><span data-stu-id="429ba-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="429ba-105">Стандартная форма учетных данных канала использует аутентификацию сертификата клиента.</span><span class="sxs-lookup"><span data-stu-id="429ba-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="429ba-106">В этом процессе клиент предоставляет сертификат TLS при подключении, а затем сервер проверяет это, прежде чем разрешить любые звонки.</span><span class="sxs-lookup"><span data-stu-id="429ba-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="429ba-107">Вы можете объединить учетные данные канала с учетными данными вызова, чтобы обеспечить полную безопасность для службы gRPC.</span><span class="sxs-lookup"><span data-stu-id="429ba-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="429ba-108">Учетные данные канала доказывают, что клиентское приложение имеет доступ к службе, а учетные данные вызова предоставляют информацию о человеке, который использует клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="429ba-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="429ba-109">Проверка подлинности сертификата клиента работает для gRPC так же, как она работает для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="429ba-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="429ba-110">Для получения дополнительной информации смотрите [проверку подлинности сертификата Настройка в ASP.NET Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="429ba-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="429ba-111">Для целей разработки можно использовать сертификат, подписанный самостоятельно, но для производства следует использовать соответствующий сертификат HTTPS, подписанный доверенным органом.</span><span class="sxs-lookup"><span data-stu-id="429ba-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="429ba-112">Добавление проверки подлинности сертификата на сервер</span><span class="sxs-lookup"><span data-stu-id="429ba-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="429ba-113">Настройка аутентификации сертификата как на уровне хоста (например, на сервере Kestrel), так и в ASP.NET конвейера Core.</span><span class="sxs-lookup"><span data-stu-id="429ba-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="429ba-114">Настройка сертификата на Kestrel</span><span class="sxs-lookup"><span data-stu-id="429ba-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="429ba-115">Вы можете настроить Kestrel (ASP.NET core HTTP сервер), чтобы требовать сертификат клиента, и по желанию провести некоторую проверку поставляемого сертификата, прежде чем принимать входящие соединения.</span><span class="sxs-lookup"><span data-stu-id="429ba-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="429ba-116">Вы делаете это `CreateWebHostBuilder` в `Program` методе класса, `Startup`а не в .</span><span class="sxs-lookup"><span data-stu-id="429ba-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="429ba-117">Настройка `ClientCertificateMode.RequireCertificate` заставляет Kestrel немедленно отклонить любой запрос на подключение, который не предоставляет сертификат клиента, но эта настройка сама по себе не будет проверять предоставленный сертификат.</span><span class="sxs-lookup"><span data-stu-id="429ba-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="429ba-118">До `ClientCertificateValidation` подключения обратного вызова, чтобы Kestrel проверил сертификат клиента в момент подключения, до того, как будет включен конвейер ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="429ba-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="429ba-119">(В этом случае обратный вызов гарантирует, что он был выдан тем же *органом сертификата,* что и сертификат сервера.)</span><span class="sxs-lookup"><span data-stu-id="429ba-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="429ba-120">Добавьте аутентификацию сертификата ASP.NET core</span><span class="sxs-lookup"><span data-stu-id="429ba-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="429ba-121">Пакет [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet обеспечивает аутентификацию сертификата.</span><span class="sxs-lookup"><span data-stu-id="429ba-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="429ba-122">Добавьте службу аутентификации сертификатов в `ConfigureServices` метод и добавьте `Configure` аутентификацию и авторизацию в ASP.NET ядро конвейера в методе.</span><span class="sxs-lookup"><span data-stu-id="429ba-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="429ba-123">Предоставление учетных данных канала в клиентском приложении</span><span class="sxs-lookup"><span data-stu-id="429ba-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="429ba-124">С `Grpc.Net.Client` помощью пакета вы настраиваете сертификаты <xref:System.Net.Http.HttpClient> на `GrpcChannel` экземпляр, который предоставляется используемому для соединения.</span><span class="sxs-lookup"><span data-stu-id="429ba-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="429ba-125">Объедините ChannelCredentials и CallCredentials</span><span class="sxs-lookup"><span data-stu-id="429ba-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="429ba-126">Вы можете настроить сервер для использования как сертификата, так и проверки подлинности маркеров.</span><span class="sxs-lookup"><span data-stu-id="429ba-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="429ba-127">Сделайте это, применяя изменения сертификата на серверЕ Kestrel и используя промежуточное программное обеспечение jWT в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="429ba-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="429ba-128">Чтобы предоставить как `ChannelCredentials` клиента, так и `CallCredentials` клиента, используйте `ChannelCredentials.Create` метод для применения учетных данных вызова.</span><span class="sxs-lookup"><span data-stu-id="429ba-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="429ba-129">Вам все еще нужно применить проверку подлинности сертификата с помощью экземпляра. <xref:System.Net.Http.HttpClient></span><span class="sxs-lookup"><span data-stu-id="429ba-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="429ba-130">Если вы передаете какие-либо аргументы конструктору, `SslCredentials` внутренний код клиента бросает исключение.</span><span class="sxs-lookup"><span data-stu-id="429ba-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="429ba-131">Параметр `SslCredentials` включен только `Grpc.Net.Client` в `Create` метод пакета для поддержания `Grpc.Core` совместимости с пакетом.</span><span class="sxs-lookup"><span data-stu-id="429ba-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="429ba-132">Вы можете `ChannelCredentials.Create` использовать метод для клиента без проверки подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="429ba-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="429ba-133">Это полезный способ передачи учетных данных маркеров с каждым вызовом, сделанным на канале.</span><span class="sxs-lookup"><span data-stu-id="429ba-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="429ba-134">Версия приложения [FullStockTicker образца gRPC с добавленной сертификатом подлинности](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) находится на GitHub.</span><span class="sxs-lookup"><span data-stu-id="429ba-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="429ba-135">[Предыдущий](call-credentials.md)
>[Следующий](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="429ba-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
