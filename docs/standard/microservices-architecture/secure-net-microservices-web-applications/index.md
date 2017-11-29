---
title: "Обеспечение безопасности веб-приложений и микрослужб .NET"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Обеспечение безопасности веб-приложений и микрослужб .NET"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 147aa099e440f5e5eb1dd6450946274aef91033a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="securing-net-microservices-and-web-applications"></a><span data-ttu-id="5df39-104">Обеспечение безопасности веб-приложений и микрослужб .NET</span><span class="sxs-lookup"><span data-stu-id="5df39-104">Securing .NET Microservices and Web Applications</span></span>

<span data-ttu-id="5df39-105">Доступ к ресурсам и интерфейсам API, предоставляемым службой, часто требуется ограничить определенным кругом надежных пользователей или клиентов.</span><span class="sxs-lookup"><span data-stu-id="5df39-105">It is often necessary for resources and APIs exposed by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="5df39-106">Первый этап принятия подобных решений о доверии на уровне API — проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="5df39-106">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="5df39-107">Проверка подлинности — это процесс достоверного установления личности пользователя.</span><span class="sxs-lookup"><span data-stu-id="5df39-107">Authentication is the process of reliably ascertaining a user’s identity.</span></span>

<span data-ttu-id="5df39-108">При использовании микрослужб управление проверкой подлинности обычно осуществляется централизованно.</span><span class="sxs-lookup"><span data-stu-id="5df39-108">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="5df39-109">Если имеется шлюз API, проверку подлинности целесообразно проводить в нем, как показано на рис. 11-1.</span><span class="sxs-lookup"><span data-stu-id="5df39-109">If you are using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 11-1.</span></span> <span data-ttu-id="5df39-110">При таком подходе отдельные микрослужбы не должны быть доступны напрямую (в обход шлюза API), если только не реализованы дополнительные средства безопасности для проверки того, поступают ли сообщения из шлюза или нет.</span><span class="sxs-lookup"><span data-stu-id="5df39-110">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![](./media/image1.png)

<span data-ttu-id="5df39-111">**Рис. 11-1**.</span><span class="sxs-lookup"><span data-stu-id="5df39-111">**Figure 11-1**.</span></span> <span data-ttu-id="5df39-112">Централизованная проверка подлинности с помощью шлюза API</span><span class="sxs-lookup"><span data-stu-id="5df39-112">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="5df39-113">Если службы доступны напрямую, для проверки подлинности пользователей можно применять службу проверки подлинности, например Azure Active Directory или выделенную микрослужбу проверки подлинности, выступающую в роли службы токенов безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="5df39-113">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="5df39-114">Сведения о доверии передаются между службами с помощью токенов безопасности или файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="5df39-114">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="5df39-115">(При необходимости они могут передаваться между приложениями в ASP.NET Core с помощью [служб защиты данных](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) Эта схема проиллюстрирована на рис. 11-2.</span><span class="sxs-lookup"><span data-stu-id="5df39-115">(These can be shared between applications, if needed, in ASP.NET Core with [data protection services](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) This pattern is illustrated in Figure 11-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="5df39-116">**Рис. 11-2**.</span><span class="sxs-lookup"><span data-stu-id="5df39-116">**Figure 11-2**.</span></span> <span data-ttu-id="5df39-117">Проверка подлинности с помощью микрослужбы удостоверений; сведения о доверии передаются посредством токена авторизации</span><span class="sxs-lookup"><span data-stu-id="5df39-117">Authentication by identity microservice; trust is shared using an authorization token</span></span>

## <a name="authenticating-using-aspnet-core-identity"></a><span data-ttu-id="5df39-118">Проверка подлинности с помощью удостоверения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5df39-118">Authenticating using ASP.NET Core Identity</span></span>

<span data-ttu-id="5df39-119">Основным механизмом для идентификации пользователей приложения в ASP.NET Core является система членства на основе [удостоверений ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="5df39-119">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="5df39-120">В удостоверении ASP.NET Core хранятся сведения о пользователе (в том числе данные для входа, роли и утверждения). Само удостоверение находится в хранилище данных, которое настраивает разработчик.</span><span class="sxs-lookup"><span data-stu-id="5df39-120">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="5df39-121">Как правило, хранилище удостоверений ASP.NET Core представляет собой хранилище Entity Framework, которое входит в состав пакета Microsoft.AspNetCore.Identity.EntityFrameworkCore.</span><span class="sxs-lookup"><span data-stu-id="5df39-121">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the Microsoft.AspNetCore.Identity.EntityFrameworkCore package.</span></span> <span data-ttu-id="5df39-122">Но вы также можете использовать пользовательские хранилища или пакеты сторонних поставщиков для хранения данных удостоверений в Хранилище таблиц Azure, DocumentDB или других системах.</span><span class="sxs-lookup"><span data-stu-id="5df39-122">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, DocumentDB, or other locations.</span></span>

<span data-ttu-id="5df39-123">Приведенный ниже код взят из шаблона проекта веб-приложения ASP.NET Core с выбранной проверкой подлинности отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5df39-123">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="5df39-124">В нем показано, как настроить удостоверение ASP.NET Core с помощью EntityFramework.Core в методе Startup.ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="5df39-124">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="5df39-125">После настройки удостоверения ASP.NET Core его необходимо включить, вызвав app.UseIdentity в методе Startup.Configure службы.</span><span class="sxs-lookup"><span data-stu-id="5df39-125">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s Startup.Configure method.</span></span>

<span data-ttu-id="5df39-126">Использование удостоверения ASP.NET Code обеспечивает несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="5df39-126">Using ASP.NET Code Identity enables several scenarios:</span></span>

-   <span data-ttu-id="5df39-127">Создание сведений о пользователе с помощью типа UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="5df39-127">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

-   <span data-ttu-id="5df39-128">Проверка подлинности пользователей с помощью типа SignInManager.</span><span class="sxs-lookup"><span data-stu-id="5df39-128">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="5df39-129">Вы можете использовать signInManager.SignInAsync для входа напрямую или signInManager.PasswordSignInAsync для проверки правильности пароля пользователя и выполнения его входа в систему.</span><span class="sxs-lookup"><span data-stu-id="5df39-129">You can use signInManager.SignInAsync to sign in directly, or signInManager.PasswordSignInAsync to confirm the user’s password is correct and then sign them in.</span></span>

-   <span data-ttu-id="5df39-130">Идентификация пользователя в соответствии со сведениями в файле cookie (которые считываются с помощью ПО промежуточного слоя удостоверения ASP.NET Core). Это позволяет включать в последующие запросы из браузера подписанное удостоверение и утверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="5df39-130">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="5df39-131">Удостоверение ASP.NET Core также поддерживает [двухфакторную проверку подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="5df39-131">ASP.NET Core Identity also supports [two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="5df39-132">Для сценариев проверки подлинности, в которых используется локальное хранилище данных пользователей и удостоверения сохраняются между запросами с помощью файлов cookie (как обычно бывает в случае с веб-приложениями MVC), удостоверение ASP.NET Core является рекомендуемым решением.</span><span class="sxs-lookup"><span data-stu-id="5df39-132">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

## <a name="authenticating-using-external-providers"></a><span data-ttu-id="5df39-133">Проверка подлинности с помощью внешних поставщиков</span><span class="sxs-lookup"><span data-stu-id="5df39-133">Authenticating using external providers</span></span>

<span data-ttu-id="5df39-134">ASP.NET Core также поддерживает использование [внешних поставщиков проверки подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/social/) для обеспечения входа пользователей посредством потоков [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="5df39-134">ASP.NET Core also supports using [external authentication providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) to let users log in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="5df39-135">Это означает, что пользователи могут выполнять вход с помощью существующих процедур проверки подлинности, предоставляемых такими поставщиками, как Майкрософт, Google, Facebook или Twitter, и связывать свои удостоверения с удостоверением ASP.NET Core в приложении.</span><span class="sxs-lookup"><span data-stu-id="5df39-135">This means that users can log in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="5df39-136">Для применения внешней проверки подлинности необходимо включить соответствующее ПО промежуточного слоя в конвейер обработки HTTP-запросов приложения.</span><span class="sxs-lookup"><span data-stu-id="5df39-136">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="5df39-137">Это ПО промежуточного слоя отвечает за обработку запросов с целью получения маршрутов URI от поставщика проверки подлинности, регистрацию сведений об удостоверениях и предоставление доступа к ним посредством метода SignInManager.GetExternalLoginInfo.</span><span class="sxs-lookup"><span data-stu-id="5df39-137">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="5df39-138">Ниже перечислены популярные внешние поставщики проверки подлинности и связанные с ними пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="5df39-138">Popular external authentication providers and their associated NuGet packages are shown below.</span></span>

<span data-ttu-id="5df39-139">**Майкрософт:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span><span class="sxs-lookup"><span data-stu-id="5df39-139">**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount</span></span>

<span data-ttu-id="5df39-140">**Google:** Microsoft.AspNetCore.Authentication.Google</span><span class="sxs-lookup"><span data-stu-id="5df39-140">**Google:** Microsoft.AspNetCore.Authentication.Google</span></span>

<span data-ttu-id="5df39-141">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span><span class="sxs-lookup"><span data-stu-id="5df39-141">**Facebook:** Microsoft.AspNetCore.Authentication.Facebook</span></span>

<span data-ttu-id="5df39-142">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span><span class="sxs-lookup"><span data-stu-id="5df39-142">**Twitter:** Microsoft.AspNetCore.Authentication.Twitter</span></span>

<span data-ttu-id="5df39-143">Во всех случаях ПО промежуточного слоя регистрируется посредством вызова метода регистрации, аналогичного методу app.Use{ExternalProvider}Authentication в Startup.Configure.</span><span class="sxs-lookup"><span data-stu-id="5df39-143">In all cases, the middleware is registered with a call to a registration method similar to app.Use{ExternalProvider}Authentication in Startup.Configure.</span></span> <span data-ttu-id="5df39-144">Методы регистрации принимают объект параметров, который содержит идентификатор приложения и секретные данные (например пароль), необходимые поставщику.</span><span class="sxs-lookup"><span data-stu-id="5df39-144">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="5df39-145">Чтобы внешние поставщики проверки подлинности могли сообщать пользователю, какое приложение запрашивает доступ к его удостоверению, приложение должно быть зарегистрировано (как описано в [документации по ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)).</span><span class="sxs-lookup"><span data-stu-id="5df39-145">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="5df39-146">После регистрации ПО промежуточного слоя в Startup.Configure можно предлагать пользователям выполнить вход при совершении любого действия контроллера.</span><span class="sxs-lookup"><span data-stu-id="5df39-146">Once the middleware is registered in Startup.Configure, you can prompt users to log in from any controller action.</span></span> <span data-ttu-id="5df39-147">Для этого нужно создать объект AuthenticationProperties, который содержит имя и URL-адрес перенаправления поставщика проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5df39-147">To do this, you create an AuthenticationProperties object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="5df39-148">После этого возвращается ответ на запрос, в котором передается объект AuthenticationProperties.</span><span class="sxs-lookup"><span data-stu-id="5df39-148">You then return a Challenge response that passes the AuthenticationProperties object.</span></span> <span data-ttu-id="5df39-149">В приведенном ниже коде показан пример.</span><span class="sxs-lookup"><span data-stu-id="5df39-149">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="5df39-150">Параметр redirectUrl содержит URL-адрес, на который внешний поставщик должен выполнить перенаправление после прохождения пользователем проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5df39-150">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="5df39-151">URL-адрес должен представлять действие, посредством которого будет выполнен вход пользователя на основании данных внешнего удостоверения, как показано в следующем упрощенном примере.</span><span class="sxs-lookup"><span data-stu-id="5df39-151">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="5df39-152">Если при создании проекта веб-приложения ASP.NET Code в Visual Studio был выбран вариант проверки подлинности **Отдельная учетная запись пользователя**, весь код, необходимый для входа посредством внешнего поставщика, уже имеется в проекте, как показано на рис. 11-3.</span><span class="sxs-lookup"><span data-stu-id="5df39-152">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 11-3.</span></span>

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

<span data-ttu-id="5df39-154">**Рис. 11-3**.</span><span class="sxs-lookup"><span data-stu-id="5df39-154">**Figure 11-3**.</span></span> <span data-ttu-id="5df39-155">Выбор способа внешней проверки подлинности при создании проекта веб-приложения</span><span class="sxs-lookup"><span data-stu-id="5df39-155">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="5df39-156">Помимо перечисленных выше внешних поставщиков проверки подлинности, доступны пакеты сторонних производителей, предоставляющие ПО промежуточного слоя для использования множества других внешних поставщиков проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5df39-156">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="5df39-157">Список см. в репозитории [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="5df39-157">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="5df39-158">Естественно, можно создать и собственное ПО промежуточного слоя для внешней проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5df39-158">It is also possible, of course, to create your own external authentication middleware.</span></span>

## <a name="authenticating-with-bearer-tokens"></a><span data-ttu-id="5df39-159">Проверка подлинности с помощью токенов носителя</span><span class="sxs-lookup"><span data-stu-id="5df39-159">Authenticating with bearer tokens</span></span>

<span data-ttu-id="5df39-160">Проверка подлинности посредством удостоверения ASP.NET Core (или посредством удостоверения и внешних поставщиков проверки подлинности) подходит для многих веб-приложений, позволяющих хранить сведения о пользователе в файле cookie.</span><span class="sxs-lookup"><span data-stu-id="5df39-160">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="5df39-161">Но в других ситуациях хранить и передавать данные в файлах cookie нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="5df39-161">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="5df39-162">Например, в веб-API ASP.NET Core, предоставляющем конечные точки с поддержкой REST, к которым могут обращаться одностраничные приложения, собственные клиенты или даже другие веб-интерфейсы API, как правило, желательно использовать проверку подлинности посредством токена носителя.</span><span class="sxs-lookup"><span data-stu-id="5df39-162">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="5df39-163">Такие приложения не работают с файлами cookie, но могут легко извлекать токен носителя и включать его в заголовок авторизации последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="5df39-163">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="5df39-164">Для проверки подлинности на основе токенов ASP.NET Core поддерживает несколько способов использования [OAuth 2.0](https://oauth.net/2/) и [OpenID Connect](http://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="5df39-164">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](http://openid.net/connect/).</span></span>

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="5df39-165">Проверка подлинности с помощью поставщика удостоверений OpenID Connect или OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="5df39-165">Authenticating with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="5df39-166">Если сведения о пользователе хранятся в Azure Active Directory или другом решении для управления удостоверениями, поддерживающем OpenID Connect или OAuth 2.0, вы можете использовать пакет Microsoft.AspNetCore.Authentication.OpenIdConnect для проверки подлинности с помощью рабочего процесса OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="5df39-166">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the Microsoft.AspNetCore.Authentication.OpenIdConnect package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="5df39-167">Например, для [проверки подлинности в Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/) веб-приложение ASP.NET Core может использовать ПО промежуточного слоя из этого пакета, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5df39-167">For example, to [authenticate against Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), an ASP.NET Core web application can use middleware from that package as shown in the following example:</span></span>

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

<span data-ttu-id="5df39-168">Значения конфигурации — это значения в Azure Active Directory, которые создаются при [регистрации приложения в качестве клиента Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="5df39-168">The configuration values are Azure Active Directory values that are created when your application is [registered as an Azure AD client](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad).</span></span> <span data-ttu-id="5df39-169">Один идентификатор клиента может использоваться несколькими микрослужбами в приложении, если им все требуется выполнять проверку подлинности пользователей посредством Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5df39-169">A single client ID can be shared among multiple microservices in an application if they all need to authenticate users authenticated via Azure Active Directory.</span></span>

<span data-ttu-id="5df39-170">Обратите внимание, что при использовании этого рабочего процесса ПО промежуточного слоя удостоверения ASP.NET Core не требуется, так как за хранение сведений о пользователях и проверку подлинности полностью отвечает Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5df39-170">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by Azure Active Directory.</span></span>

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="5df39-171">Выпуск токенов безопасности службой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5df39-171">Issuing security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="5df39-172">Если вы предпочитаете выпускать токены безопасности для локальных пользователей удостоверения ASP.NET Core, а не использовать внешний поставщик удостоверений, то вы можете прибегнуть к ряду полезных библиотек сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="5df39-172">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="5df39-173">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) и [OpenIddict](https://github.com/openiddict/openiddict-core) — это поставщики OpenID Connect, которые легко интегрируются с удостоверением ASP.NET Core и позволяют выпускать токены безопасности из службы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="5df39-173">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="5df39-174">В [документации по IdentityServer4](https://identityserver4.readthedocs.io/en/release/) приведены подробные инструкции по работе с этой библиотекой.</span><span class="sxs-lookup"><span data-stu-id="5df39-174">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/release/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="5df39-175">Ниже описываются основные действия по использованию IdentityServer4 для выпуска токенов.</span><span class="sxs-lookup"><span data-stu-id="5df39-175">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1.  <span data-ttu-id="5df39-176">Вызовите app.UseIdentityServer в методе Startup.Configure, чтобы добавить IdentityServer4 в конвейер обработки HTTP-запросов приложения.</span><span class="sxs-lookup"><span data-stu-id="5df39-176">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="5df39-177">Это позволит библиотеке обрабатывать запросы к конечным точкам OpenID Connect и OAuth2 как /connect/token.</span><span class="sxs-lookup"><span data-stu-id="5df39-177">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2.  <span data-ttu-id="5df39-178">Настройте IdentityServer4 в методе Startup.ConfigureServices, выполнив вызов services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="5df39-178">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3.  <span data-ttu-id="5df39-179">Чтобы настроить сервер удостоверений, нужно предоставить следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5df39-179">You configure identity server by providing the following data:</span></span>

-   <span data-ttu-id="5df39-180">[учетные данные](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) для входа;</span><span class="sxs-lookup"><span data-stu-id="5df39-180">The [credentials](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) to use for signing.</span></span>

-   <span data-ttu-id="5df39-181">[ресурсы удостоверений и API](https://identityserver4.readthedocs.io/en/release/topics/resources.html), к которым пользователи могут запрашивать доступ:</span><span class="sxs-lookup"><span data-stu-id="5df39-181">The [Identity and API resources](https://identityserver4.readthedocs.io/en/release/topics/resources.html) that users might request access to:</span></span>

<!-- -->

-   <span data-ttu-id="5df39-182">ресурсы API представляют защищенные данные или функциональные возможности, к которым пользователь может получать доступ с помощью токена доступа;</span><span class="sxs-lookup"><span data-stu-id="5df39-182">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="5df39-183">примером ресурса API может служить веб-API (или набор веб-API), требующий авторизации;</span><span class="sxs-lookup"><span data-stu-id="5df39-183">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

-   <span data-ttu-id="5df39-184">ресурсы удостоверений представляют сведения (утверждения), которые предоставляются клиенту для идентификации пользователя;</span><span class="sxs-lookup"><span data-stu-id="5df39-184">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="5df39-185">утверждения могут включать имя пользователя, адрес электронной почты и другие данные;</span><span class="sxs-lookup"><span data-stu-id="5df39-185">The claims might include the user name, email address, and so on.</span></span>

<!-- -->

-   <span data-ttu-id="5df39-186">[клиенты](https://identityserver4.readthedocs.io/en/release/topics/clients.html), которые будут подключаться для запроса токенов;</span><span class="sxs-lookup"><span data-stu-id="5df39-186">The [clients](https://identityserver4.readthedocs.io/en/release/topics/clients.html) that will be connecting in order to request tokens.</span></span>

-   <span data-ttu-id="5df39-187">механизм хранения сведений о пользователях, например [удостоверение ASP.NET Core](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) или иной.</span><span class="sxs-lookup"><span data-stu-id="5df39-187">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) or an alternative.</span></span>

<span data-ttu-id="5df39-188">При указании клиентов и ресурсов, используемых IdentityServer4, можно передать коллекцию IEnumerable&lt;T&gt; соответствующего типа в методы, которые принимают хранилища клиентов или ресурсов в памяти.</span><span class="sxs-lookup"><span data-stu-id="5df39-188">When you specify clients and resources for IdentityServer4 to use, you can pass an IEnumerable&lt;T&gt; collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="5df39-189">В более сложных сценариях типы клиентов или поставщиков ресурсов можно предоставлять с помощью внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="5df39-189">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="5df39-190">Ниже приведен пример конфигурации для IdentityServer4, которая предполагает использование клиентов и ресурсов в памяти, предоставляемых пользовательским типом IClientStore.</span><span class="sxs-lookup"><span data-stu-id="5df39-190">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a><span data-ttu-id="5df39-191">Использование токенов безопасности</span><span class="sxs-lookup"><span data-stu-id="5df39-191">Consuming security tokens</span></span>

<span data-ttu-id="5df39-192">Проверка подлинности в конечной точке OpenID Connect или выпуск собственных токенов безопасности подходят для некоторых ситуаций.</span><span class="sxs-lookup"><span data-stu-id="5df39-192">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="5df39-193">Но что если службе нужно просто предоставлять доступ только тем пользователям, у которых есть действительные токены безопасности, предоставленные другой службой?</span><span class="sxs-lookup"><span data-stu-id="5df39-193">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="5df39-194">Для такого случая в составе пакета Microsoft.AspNetCore.Authentication.JwtBearer доступно ПО промежуточного слоя, обрабатывающее токены JWT.</span><span class="sxs-lookup"><span data-stu-id="5df39-194">For that scenario, authentication middleware that handles JWT tokens is available in the Microsoft.AspNetCore.Authentication.JwtBearer package.</span></span> <span data-ttu-id="5df39-195">JWT расшифровывается как [JSON Web Token](https://tools.ietf.org/html/rfc7519) (веб-токен JSON). Это распространенный формат токенов безопасности (определенный в документе RFC 7519) для передачи утверждений безопасности.</span><span class="sxs-lookup"><span data-stu-id="5df39-195">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="5df39-196">Ниже приведен простой пример использования таких токенов с помощью ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="5df39-196">A simple example of how to use middleware to consume such tokens might look like the following example.</span></span> <span data-ttu-id="5df39-197">Этот код должен предшествовать вызовам ПО промежуточного слоя MVC ASP.NET Core (app.UseMvc).</span><span class="sxs-lookup"><span data-stu-id="5df39-197">This code must precede calls to ASP.NET Core MVC middleware (app.UseMvc).</span></span>

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

<span data-ttu-id="5df39-198">В примере используются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="5df39-198">The parameters in this usage are:</span></span>

-   <span data-ttu-id="5df39-199">Audience представляет получателя входящего токена или ресурса, к которому токен предоставляет доступ.</span><span class="sxs-lookup"><span data-stu-id="5df39-199">Audience represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="5df39-200">Если значение этого параметра не совпадает со значением параметра aud в токене, токен будет отклонен.</span><span class="sxs-lookup"><span data-stu-id="5df39-200">If the value specified in this parameter does not match the aud parameter in the token, the token will be rejected.</span></span>

-   <span data-ttu-id="5df39-201">Authority — это адрес сервера проверки подлинности, выпустившего токен.</span><span class="sxs-lookup"><span data-stu-id="5df39-201">Authority is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="5df39-202">ПО промежуточного слоя для проверки подлинности носителя JWT использует этот универсальный код ресурса (URI) для получения открытого ключа, с помощью которого можно проверить подпись токена.</span><span class="sxs-lookup"><span data-stu-id="5df39-202">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="5df39-203">ПО промежуточного слоя также проверяет, совпадает ли значение параметра iss в токене с этим кодом URI.</span><span class="sxs-lookup"><span data-stu-id="5df39-203">The middleware also confirms that the iss parameter in the token matches this URI.</span></span>

-   <span data-ttu-id="5df39-204">AutomaticAuthenticate — это логическое значение, которое указывает, должен ли пользователь, определяемый токеном, входить в систему автоматически.</span><span class="sxs-lookup"><span data-stu-id="5df39-204">AutomaticAuthenticate is a Boolean value that indicates whether the user defined by the token should be automatically signed in.</span></span>

<span data-ttu-id="5df39-205">Еще один параметр, RequireHttpsMetadata, в этом примере не используется.</span><span class="sxs-lookup"><span data-stu-id="5df39-205">Another parameter, RequireHttpsMetadata, is not used in this example.</span></span> <span data-ttu-id="5df39-206">Он полезен для тестирования. Присвоив ему значение false, можно проводить тестирование в средах, в которых нет сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5df39-206">It is useful for testing purposes; you set this parameter to false so that you can test in environments where you do not have certificates.</span></span> <span data-ttu-id="5df39-207">В реальных развертываниях токены носителя JWT следует передавать только по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5df39-207">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="5df39-208">При наличии этого ПО промежуточного слоя токены JWT автоматически извлекаются из заголовков авторизации.</span><span class="sxs-lookup"><span data-stu-id="5df39-208">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="5df39-209">Затем они десериализуются, проверяются (на основе значений параметров Audience и Authority) и сохраняются как сведения о пользователе для дальнейшего использования действиями MVC или фильтрами авторизации.</span><span class="sxs-lookup"><span data-stu-id="5df39-209">They are then deserialized, validated (using the values in the Audience and Authority parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="5df39-210">ПО промежуточного слоя для проверки подлинности носителя JWT может поддерживать и более сложные сценарии, например проверку токена с помощью локального сертификата, если центр сертификации недоступен.</span><span class="sxs-lookup"><span data-stu-id="5df39-210">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="5df39-211">В этом случае можно задать объект TokenValidationParameters в объекте JwtBearerOptions.</span><span class="sxs-lookup"><span data-stu-id="5df39-211">For this scenario, you can specify a TokenValidationParameters object in the JwtBearerOptions object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5df39-212">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="5df39-212">Additional resources</span></span>

-   <span data-ttu-id="5df39-213">**Совместное использование файлов cookie приложениями**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span><span class="sxs-lookup"><span data-stu-id="5df39-213">**Sharing cookies between applications**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)</span></span>

-   <span data-ttu-id="5df39-214">**Общие сведения об удостоверении**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="5df39-214">**Introduction to Identity**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="5df39-215">**Рик Андерсон (Rick Anderson). Двухфакторная проверка подлинности с использованием SMS**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span><span class="sxs-lookup"><span data-stu-id="5df39-215">**Rick Anderson. Two-factor authentication with SMS**
[*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)</span></span>

-   <span data-ttu-id="5df39-216">**Обеспечение проверки подлинности с помощью Facebook, Google и других внешних поставщиков**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span><span class="sxs-lookup"><span data-stu-id="5df39-216">**Enabling authentication using Facebook, Google and other external providers**
[*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)</span></span>

-   <span data-ttu-id="5df39-217">**Мичелл Аникас (Michell Anicas). Введение в OAuth 2**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span><span class="sxs-lookup"><span data-stu-id="5df39-217">**Michell Anicas. An Introduction to OAuth 2**
[*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)</span></span>

-   <span data-ttu-id="5df39-218">**AspNet.Security.OAuth.Providers** (репозиторий GitHub для поставщиков OAuth в ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="5df39-218">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers.</span></span>
    [<span data-ttu-id="5df39-219">*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*</span><span class="sxs-lookup"><span data-stu-id="5df39-219">*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*</span></span>](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   <span data-ttu-id="5df39-220">**Дэнни Строкис (Danny Strockis). Интеграция Azure AD с веб-приложением ASP.NET Core**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span><span class="sxs-lookup"><span data-stu-id="5df39-220">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app**
[*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)</span></span>

-   <span data-ttu-id="5df39-221">**IdentityServer4. Официальная документация**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span><span class="sxs-lookup"><span data-stu-id="5df39-221">**IdentityServer4. Official documentation**
[*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5df39-222">[Назад] (../implement-resilient-applications/monitor-app-health.md) [Далее] (authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="5df39-222">[Previous] (../implement-resilient-applications/monitor-app-health.md) [Next] (authorization-net-microservices-web-applications.md)</span></span>
