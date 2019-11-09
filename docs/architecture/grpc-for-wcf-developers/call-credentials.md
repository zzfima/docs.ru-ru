---
title: Вызов учетных данных — gRPC для разработчиков WCF
description: Как реализовать и использовать учетные данные вызова gRPC в ASP.NET Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f29d69ec37fe60bcd7ca01391001ea9eb71e7e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841675"
---
# <a name="call-credentials"></a><span data-ttu-id="a9aa1-103">Учетные данные вызова</span><span class="sxs-lookup"><span data-stu-id="a9aa1-103">Call credentials</span></span>

<span data-ttu-id="a9aa1-104">Учетные данные вызова зависят от какого либо маркера, переданного в метаданных с каждым запросом.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-104">Call credentials are all based on some kind of token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="a9aa1-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="a9aa1-105">WS-Federation</span></span>

<span data-ttu-id="a9aa1-106">ASP.NET Core поддерживает WS-Federation с помощью пакета NuGet [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) .</span><span class="sxs-lookup"><span data-stu-id="a9aa1-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="a9aa1-107">WS-Federation — это ближайшая доступная альтернатива к проверке подлинности Windows, которая не поддерживается по протоколу HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-107">WS-Federation is the closest available alternative to Windows Authentication, which is not supported over HTTP/2.</span></span> <span data-ttu-id="a9aa1-108">Пользователи проходят проверку подлинности с помощью службы федерации Active Directory (AD FS) (ADFS), которая предоставляет маркер, который можно использовать для проверки подлинности с помощью ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-108">Users are authenticated using Active Directory Federation Services (ADFS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="a9aa1-109">Дополнительные сведения о том, как приступить к работе с этим методом проверки подлинности, см. в статье [Проверка подлинности пользователей с помощью WS-Federation в ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="a9aa1-109">For more information on how to get started with this authentication method, see the [Authenticate users with WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) article.</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="a9aa1-110">Токены носителя JWT</span><span class="sxs-lookup"><span data-stu-id="a9aa1-110">JWT Bearer tokens</span></span>

<span data-ttu-id="a9aa1-111">[JSON Web Token](https://jwt.io) Standard предоставляет способ кодирования сведений о пользователе и их утверждениях в закодированной строке, а также для подписи маркера таким образом, чтобы потребитель мог проверить целостность маркера с помощью шифрования с открытым ключом.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-111">The [JSON Web Token](https://jwt.io) standard provides a way to encode information about a user and their claims in an encoded string, and to sign that token in such a way that the consumer can verify the integrity of the token using public key cryptography.</span></span> <span data-ttu-id="a9aa1-112">Можно использовать различные службы, например IdentityServer4, для проверки подлинности пользователей и создания маркеров OpenID Connect Connect (OIDC) для использования с gRPC и API HTTP.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-112">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="a9aa1-113">ASP.NET Core 3,0 может управлять веб-маркерами JSON с помощью пакета носителя JWT.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-113">ASP.NET Core 3.0 can handle JSON Web Tokens using the JWT Bearer package.</span></span> <span data-ttu-id="a9aa1-114">Конфигурация одинакова для приложения gRPC в качестве ASP.NET Core приложения MVC.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-114">The configuration is exactly the same for a gRPC application as an ASP.NET Core MVC application.</span></span>

<span data-ttu-id="a9aa1-115">В этой главе основное внимание уделяется маркерам носителя JWT, так как их проще разрабатывать, чем WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-115">This chapter will focus on JWT Bearer tokens as they're easier to develop with than WS-Federation.</span></span>

## <a name="adding-authentication-and-authorization-to-the-server"></a><span data-ttu-id="a9aa1-116">Добавление проверки подлинности и авторизации на сервер</span><span class="sxs-lookup"><span data-stu-id="a9aa1-116">Adding authentication and authorization to the server</span></span>

<span data-ttu-id="a9aa1-117">Пакет носителя JWT не входит в ASP.NET Core 3,0 по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-117">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="a9aa1-118">Установите пакет NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) в приложении.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-118">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="a9aa1-119">Добавьте службу проверки подлинности в класс Startup и настройте обработчик носителя JWT.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-119">Add the Authentication service in the Startup class and configure the JWT Bearer handler.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

<span data-ttu-id="a9aa1-120">Для свойства `IssuerSigningKey` требуется реализация `Microsoft.IdentityModels.Tokens.SecurityKey` с криптографическими данными, необходимыми для проверки подписанных токенов.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-120">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="a9aa1-121">Этот маркер должен быть безопасно сохранен на *сервере секретности* , например Azure KeyVault.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-121">This token should be stored securely in a *secrets server* like Azure KeyVault.</span></span>

<span data-ttu-id="a9aa1-122">Затем добавьте службу авторизации, которая управляет доступом к системе.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-122">Next add the Authorization service, which controls access to the system.</span></span>

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> <span data-ttu-id="a9aa1-123">Проверка подлинности и авторизация — это два отдельных шага.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-123">Authentication and Authorization are two separate steps.</span></span> <span data-ttu-id="a9aa1-124">Для определения удостоверения пользователя используется проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-124">Authentication is used to determine the user's identity.</span></span> <span data-ttu-id="a9aa1-125">Авторизация определяет, разрешено ли этому пользователю доступ к различным частям системы.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-125">Authorization decides whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="a9aa1-126">Теперь добавьте по промежуточного слоя проверки подлинности и авторизации в конвейер ASP.NET Core в методе `Configure`.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-126">Now add the Authentication and Authorization middleware to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="a9aa1-127">Наконец, примените атрибут `[Authorize]` к любым службам или методам, которые необходимо защитить, и используйте свойство `User` из базового `HttpContext` для проверки разрешений.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-127">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="providing-call-credentials-in-the-client-application"></a><span data-ttu-id="a9aa1-128">Предоставление учетных данных вызова в клиентском приложении</span><span class="sxs-lookup"><span data-stu-id="a9aa1-128">Providing call credentials in the client application</span></span>

<span data-ttu-id="a9aa1-129">После получения маркера JWT с сервера удостоверений его можно использовать для проверки подлинности вызовов gRPC из клиента, добавив его в качестве заголовка метаданных в вызове следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a9aa1-129">Once you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

<span data-ttu-id="a9aa1-130">Теперь вы защитили службу gRPC с помощью токенов носителя JWT в качестве учетных данных вызова.</span><span class="sxs-lookup"><span data-stu-id="a9aa1-130">Now, you've secured your gRPC service using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="a9aa1-131">В GitHub будет [добавлена версия примера gRPC приложения с проверкой подлинности и авторизацией](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) .</span><span class="sxs-lookup"><span data-stu-id="a9aa1-131">A version of the [Portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a9aa1-132">[Назад](security.md)
>[Вперед](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="a9aa1-132">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
