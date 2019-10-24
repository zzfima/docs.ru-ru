---
title: Обеспечение безопасности веб-приложений и микрослужб .NET
description: Безопасность микрослужб и веб-приложений .NET — узнайте о способах проверки подлинности в веб-приложениях ASP.NET Core.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 5e9b616e0443e85c016401a51efc3b04d2329e3b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771988"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="71b1f-103">Обеспечение безопасности микрослужб и веб-приложений .NET</span><span class="sxs-lookup"><span data-stu-id="71b1f-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="71b1f-104">Существует так много аспектов безопасности микрослужб и веб-приложений, что эта тема может легко занять несколько книг, поэтому в этом разделе мы сосредоточимся на проверке подлинности, авторизации и секретах приложений.</span><span class="sxs-lookup"><span data-stu-id="71b1f-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="71b1f-105">Внедрение проверки подлинности в микрослужбы и веб-приложения .NET</span><span class="sxs-lookup"><span data-stu-id="71b1f-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="71b1f-106">Доступ к ресурсам и API-интерфейсам, публикуемым службой, часто требуется ограничить определенным кругом надежных пользователей или клиентов.</span><span class="sxs-lookup"><span data-stu-id="71b1f-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="71b1f-107">Первый этап принятия подобных решений о доверии на уровне API — проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="71b1f-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="71b1f-108">Проверка подлинности — это процесс достоверного установления личности пользователя.</span><span class="sxs-lookup"><span data-stu-id="71b1f-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="71b1f-109">При использовании микрослужб управление проверкой подлинности обычно осуществляется централизованно.</span><span class="sxs-lookup"><span data-stu-id="71b1f-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="71b1f-110">Если имеется шлюз API, проверку подлинности целесообразно проводить в нем, как показано на рис. 9-1.</span><span class="sxs-lookup"><span data-stu-id="71b1f-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="71b1f-111">При таком подходе отдельные микрослужбы не должны быть доступны напрямую (в обход шлюза API), если только не реализованы дополнительные средства безопасности для проверки того, поступают ли сообщения из шлюза или нет.</span><span class="sxs-lookup"><span data-stu-id="71b1f-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Когда шлюз API централизует проверку подлинности, он добавляет сведения о пользователе при переадресации запросов в микрослужбы.](./media/image1.png)

<span data-ttu-id="71b1f-113">**Рис. 9-1**.</span><span class="sxs-lookup"><span data-stu-id="71b1f-113">**Figure 9-1**.</span></span> <span data-ttu-id="71b1f-114">Централизованная проверка подлинности с помощью шлюза API</span><span class="sxs-lookup"><span data-stu-id="71b1f-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="71b1f-115">Если службы доступны напрямую, для проверки подлинности пользователей можно применять службу проверки подлинности, например Azure Active Directory или выделенную микрослужбу проверки подлинности, выступающую в роли службы токенов безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="71b1f-115">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="71b1f-116">Сведения о доверии передаются между службами с помощью токенов безопасности или файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="71b1f-116">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="71b1f-117">(При необходимости эти токены могут передаваться между приложениями ASP.NET Core путем реализации [совместного использования файлов cookie](/aspnet/core/security/cookie-sharing).) Такая схема проиллюстрирована на рис. 9-2.</span><span class="sxs-lookup"><span data-stu-id="71b1f-117">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![При прямом доступе к микрослужбам доверие, включающее проверку подлинности и авторизацию, обрабатывается общим для всех токеном безопасности, который выдает специализированная микрослужба.](./media/image2.png)

<span data-ttu-id="71b1f-119">**Рис. 9-2**.</span><span class="sxs-lookup"><span data-stu-id="71b1f-119">**Figure 9-2**.</span></span> <span data-ttu-id="71b1f-120">Проверка подлинности с помощью микрослужбы удостоверений; сведения о доверии передаются посредством токена авторизации</span><span class="sxs-lookup"><span data-stu-id="71b1f-120">Authentication by identity microservice; trust is shared using an authorization token</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="71b1f-121">Проверка подлинности с помощью ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="71b1f-121">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="71b1f-122">Основным механизмом для идентификации пользователей приложения в ASP.NET Core является система членства на основе [удостоверений ASP.NET Core](/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="71b1f-122">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="71b1f-123">В удостоверении ASP.NET Core хранятся сведения о пользователе (в том числе данные для входа, роли и утверждения). Само удостоверение находится в хранилище данных, которое настраивает разработчик.</span><span class="sxs-lookup"><span data-stu-id="71b1f-123">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="71b1f-124">Как правило, хранилище данных ASP.NET Core Identity представляет собой хранилище Entity Framework, входящее в пакет `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="71b1f-124">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="71b1f-125">Однако вы также можете использовать настраиваемые хранилища или пакеты сторонних поставщиков для хранения сведений удостоверений в Хранилище таблиц Azure, CosmosDB или других местах.</span><span class="sxs-lookup"><span data-stu-id="71b1f-125">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

<span data-ttu-id="71b1f-126">Приведенный ниже код взят из шаблона проекта веб-приложения ASP.NET Core с выбранной проверкой подлинности отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="71b1f-126">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="71b1f-127">В нем показано, как настроить удостоверение ASP.NET Core с помощью EntityFramework.Core в методе Startup.ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="71b1f-127">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="71b1f-128">После настройки службы ASP.NET Core Indentity ее необходимо включить, вызвав app.UseIdentity в методе службы `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="71b1f-128">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s `Startup.Configure` method.</span></span>

<span data-ttu-id="71b1f-129">Использование удостоверения ASP.NET Core обеспечивает несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="71b1f-129">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="71b1f-130">Создание сведений о пользователе с помощью типа UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="71b1f-130">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="71b1f-131">Проверка подлинности пользователей с помощью типа SignInManager.</span><span class="sxs-lookup"><span data-stu-id="71b1f-131">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="71b1f-132">Вы можете использовать `signInManager.SignInAsync` для входа напрямую или `signInManager.PasswordSignInAsync` для проверки пользовательского пароля и последующего входа.</span><span class="sxs-lookup"><span data-stu-id="71b1f-132">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="71b1f-133">Идентификация пользователя в соответствии со сведениями в файле cookie (которые считываются с помощью ПО промежуточного слоя удостоверения ASP.NET Core). Это позволяет включать в последующие запросы из браузера подписанное удостоверение и утверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="71b1f-133">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="71b1f-134">Удостоверение ASP.NET Core также поддерживает [двухфакторную проверку подлинности](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="71b1f-134">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="71b1f-135">Для сценариев проверки подлинности, в которых используется локальное хранилище данных пользователей и удостоверения сохраняются между запросами с помощью файлов cookie (как обычно бывает в случае с веб-приложениями MVC), удостоверение ASP.NET Core является рекомендуемым решением.</span><span class="sxs-lookup"><span data-stu-id="71b1f-135">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="71b1f-136">Проверка подлинности с помощью внешних поставщиков</span><span class="sxs-lookup"><span data-stu-id="71b1f-136">Authenticate with external providers</span></span>

<span data-ttu-id="71b1f-137">ASP.NET Core также поддерживает использование [внешних поставщиков проверки подлинности](/aspnet/core/security/authentication/social/) для обеспечения входа пользователей посредством рабочих процессов [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="71b1f-137">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="71b1f-138">Это означает, что пользователи могут выполнять вход с помощью существующих процедур проверки подлинности, предоставляемых такими поставщиками, как Майкрософт, Google, Facebook или Twitter, и связывать свои удостоверения с удостоверением ASP.NET Core в вашем приложении.</span><span class="sxs-lookup"><span data-stu-id="71b1f-138">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="71b1f-139">Для применения внешней проверки подлинности необходимо включить соответствующее ПО промежуточного слоя в конвейер обработки HTTP-запросов приложения.</span><span class="sxs-lookup"><span data-stu-id="71b1f-139">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="71b1f-140">Это ПО промежуточного слоя отвечает за обработку запросов с целью получения маршрутов URI от поставщика проверки подлинности, регистрацию сведений об удостоверениях и предоставление доступа к ним посредством метода SignInManager.GetExternalLoginInfo.</span><span class="sxs-lookup"><span data-stu-id="71b1f-140">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="71b1f-141">В следующей таблице показаны популярные внешние поставщики проверки подлинности и связанные с ними пакеты NuGet:</span><span class="sxs-lookup"><span data-stu-id="71b1f-141">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="71b1f-142">**Поставщик**</span><span class="sxs-lookup"><span data-stu-id="71b1f-142">**Provider**</span></span>  | <span data-ttu-id="71b1f-143">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="71b1f-143">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="71b1f-144">**Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="71b1f-144">**Microsoft**</span></span> | <span data-ttu-id="71b1f-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="71b1f-145">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="71b1f-146">**Google**</span><span class="sxs-lookup"><span data-stu-id="71b1f-146">**Google**</span></span>    | <span data-ttu-id="71b1f-147">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="71b1f-147">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="71b1f-148">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="71b1f-148">**Facebook**</span></span>  | <span data-ttu-id="71b1f-149">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="71b1f-149">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="71b1f-150">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="71b1f-150">**Twitter**</span></span>   | <span data-ttu-id="71b1f-151">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="71b1f-151">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="71b1f-152">Во всех случаях ПО промежуточного слоя регистрируется через вызов метода регистрации, аналогично `app.Use{ExternalProvider}Authentication` в `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="71b1f-152">In all cases, the middleware is registered with a call to a registration method similar to `app.Use{ExternalProvider}Authentication` in `Startup.Configure`.</span></span> <span data-ttu-id="71b1f-153">Методы регистрации принимают объект параметров, который содержит идентификатор приложения и секретные данные (например пароль), необходимые поставщику.</span><span class="sxs-lookup"><span data-stu-id="71b1f-153">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="71b1f-154">Чтобы внешние поставщики проверки подлинности могли сообщать пользователю, какое приложение запрашивает доступ к его удостоверению, приложение должно быть зарегистрировано (как описано в [документации по ASP.NET Core](/aspnet/core/security/authentication/social/)).</span><span class="sxs-lookup"><span data-stu-id="71b1f-154">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="71b1f-155">После регистрации ПО промежуточного слоя в `Startup.Configure` вы можете запрашивать у пользователей вход в любом действии контроллера.</span><span class="sxs-lookup"><span data-stu-id="71b1f-155">Once the middleware is registered in `Startup.Configure`, you can prompt users to sign in from any controller action.</span></span> <span data-ttu-id="71b1f-156">Для этого нужно создать объект `AuthenticationProperties`, который содержит имя и URL-адрес перенаправления поставщика проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="71b1f-156">To do this, you create an `AuthenticationProperties` object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="71b1f-157">Затем нужно вернуть ответ на запрос и передать в нем объект `AuthenticationProperties`.</span><span class="sxs-lookup"><span data-stu-id="71b1f-157">You then return a Challenge response that passes the `AuthenticationProperties` object.</span></span> <span data-ttu-id="71b1f-158">В приведенном ниже коде показан пример.</span><span class="sxs-lookup"><span data-stu-id="71b1f-158">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="71b1f-159">Параметр redirectUrl содержит URL-адрес, на который внешний поставщик должен выполнить перенаправление после прохождения пользователем проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="71b1f-159">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="71b1f-160">URL-адрес должен представлять действие, посредством которого будет выполнен вход пользователя на основании данных внешнего удостоверения, как показано в следующем упрощенном примере.</span><span class="sxs-lookup"><span data-stu-id="71b1f-160">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

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

<span data-ttu-id="71b1f-161">Если при создании проекта веб-приложения ASP.NET Code в Visual Studio выбрать вариант проверки подлинности **Отдельная учетная запись пользователя**, то весь код, необходимый для входа через внешнего поставщика, уже будет доступен в проекте, как показано на рис. 9-3.</span><span class="sxs-lookup"><span data-stu-id="71b1f-161">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 9-3.</span></span>

![Диалоговое окно для нового веб-приложения ASP.NET Core, в котором выделена кнопка изменения проверки подлинности.](./media/image3.png)

<span data-ttu-id="71b1f-163">**Рис. 9-3**.</span><span class="sxs-lookup"><span data-stu-id="71b1f-163">**Figure 9-3**.</span></span> <span data-ttu-id="71b1f-164">Выбор способа внешней проверки подлинности при создании проекта веб-приложения</span><span class="sxs-lookup"><span data-stu-id="71b1f-164">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="71b1f-165">Помимо перечисленных выше внешних поставщиков проверки подлинности, доступны пакеты сторонних производителей, предоставляющие ПО промежуточного слоя для использования множества других внешних поставщиков проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="71b1f-165">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="71b1f-166">Список см. в репозитории [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="71b1f-166">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="71b1f-167">Вы также можете создать собственное ПО промежуточного слоя для внешней проверки подлинности, позволяющее решать какие-то особые задачи.</span><span class="sxs-lookup"><span data-stu-id="71b1f-167">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="71b1f-168">Проверка подлинности с помощью токенов носителя</span><span class="sxs-lookup"><span data-stu-id="71b1f-168">Authenticate with bearer tokens</span></span>

<span data-ttu-id="71b1f-169">Проверка подлинности посредством удостоверения ASP.NET Core (или посредством удостоверения и внешних поставщиков проверки подлинности) подходит для многих веб-приложений, позволяющих хранить сведения о пользователе в файле cookie.</span><span class="sxs-lookup"><span data-stu-id="71b1f-169">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="71b1f-170">Но в других ситуациях хранить и передавать данные в файлах cookie нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="71b1f-170">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="71b1f-171">Например, в веб-API ASP.NET Core, предоставляющем конечные точки с поддержкой REST, к которым могут обращаться одностраничные приложения, собственные клиенты или даже другие веб-интерфейсы API, как правило, желательно использовать проверку подлинности посредством токена носителя.</span><span class="sxs-lookup"><span data-stu-id="71b1f-171">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="71b1f-172">Такие приложения не работают с файлами cookie, но могут легко извлекать токен носителя и включать его в заголовок авторизации последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="71b1f-172">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="71b1f-173">Для проверки подлинности на основе токенов ASP.NET Core поддерживает несколько способов использования [OAuth 2.0](https://oauth.net/2/) и [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="71b1f-173">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="71b1f-174">Проверка подлинности с помощью поставщика удостоверений OpenID Connect или OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="71b1f-174">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="71b1f-175">Если сведения о пользователе хранятся в Azure Active Directory или другом решении для управления удостоверениями, поддерживающем OpenID Connect или OAuth 2.0, вы можете использовать пакет **Microsoft.AspNetCore.Authentication.OpenIdConnect** для проверки подлинности с помощью рабочего процесса OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="71b1f-175">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="71b1f-176">Например, для проверки подлинности в микрослужбе Identity.Api из eShopOnContainers веб-приложение ASP.NET Core может использовать ПО промежуточного слоя из этого пакета, как показано в следующем упрощенном примере `Startup.cs`:</span><span class="sxs-lookup"><span data-stu-id="71b1f-176">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="71b1f-177">Обратите внимание, что при использовании этого рабочего процесса ПО промежуточного слоя ASP.NET Core Identity не требуется, так как за хранение сведений о пользователях и проверку подлинности полностью отвечает служба Identity.</span><span class="sxs-lookup"><span data-stu-id="71b1f-177">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="71b1f-178">Выпуск токенов безопасности службой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="71b1f-178">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="71b1f-179">Если вы предпочитаете выпускать токены безопасности для локальных пользователей удостоверения ASP.NET Core, а не использовать внешний поставщик удостоверений, то вы можете прибегнуть к ряду полезных библиотек сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="71b1f-179">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="71b1f-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) и [OpenIddict](https://github.com/openiddict/openiddict-core) — это поставщики OpenID Connect, которые легко интегрируются с удостоверением ASP.NET Core и позволяют выпускать токены безопасности из службы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="71b1f-180">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="71b1f-181">В [документации по IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) приведены подробные инструкции по работе с этой библиотекой.</span><span class="sxs-lookup"><span data-stu-id="71b1f-181">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="71b1f-182">Ниже описываются основные действия по использованию IdentityServer4 для выпуска токенов.</span><span class="sxs-lookup"><span data-stu-id="71b1f-182">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="71b1f-183">Вызовите app.UseIdentityServer в методе Startup.Configure, чтобы добавить IdentityServer4 в конвейер обработки HTTP-запросов приложения.</span><span class="sxs-lookup"><span data-stu-id="71b1f-183">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="71b1f-184">Это позволит библиотеке обрабатывать запросы к конечным точкам OpenID Connect и OAuth2 как /connect/token.</span><span class="sxs-lookup"><span data-stu-id="71b1f-184">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="71b1f-185">Настройте IdentityServer4 в методе Startup.ConfigureServices, выполнив вызов services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="71b1f-185">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="71b1f-186">Чтобы настроить сервер удостоверений, нужно задать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="71b1f-186">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="71b1f-187">[учетные данные](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) для входа;</span><span class="sxs-lookup"><span data-stu-id="71b1f-187">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="71b1f-188">[ресурсы удостоверений и API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html), к которым пользователи могут запрашивать доступ:</span><span class="sxs-lookup"><span data-stu-id="71b1f-188">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="71b1f-189">ресурсы API представляют защищенные данные или функциональные возможности, к которым пользователь может получать доступ с помощью токена доступа;</span><span class="sxs-lookup"><span data-stu-id="71b1f-189">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="71b1f-190">примером ресурса API может служить веб-API (или набор веб-API), требующий авторизации;</span><span class="sxs-lookup"><span data-stu-id="71b1f-190">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="71b1f-191">ресурсы удостоверений представляют сведения (утверждения), которые предоставляются клиенту для идентификации пользователя;</span><span class="sxs-lookup"><span data-stu-id="71b1f-191">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="71b1f-192">утверждения могут включать имя пользователя, адрес электронной почты и другие данные;</span><span class="sxs-lookup"><span data-stu-id="71b1f-192">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="71b1f-193">[клиенты](https://identityserver4.readthedocs.io/en/latest/topics/clients.html), которые будут подключаться для запроса токенов;</span><span class="sxs-lookup"><span data-stu-id="71b1f-193">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="71b1f-194">механизм хранения сведений о пользователях, например [удостоверение ASP.NET Core](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) или иной.</span><span class="sxs-lookup"><span data-stu-id="71b1f-194">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="71b1f-195">При указании клиентов и ресурсов, используемых IdentityServer4, вы можете передать коллекцию <xref:System.Collections.Generic.IEnumerable%601> соответствующего типа в методы, которые принимают хранилища клиентов или ресурсов в памяти.</span><span class="sxs-lookup"><span data-stu-id="71b1f-195">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="71b1f-196">В более сложных сценариях типы клиентов или поставщиков ресурсов можно предоставлять с помощью внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="71b1f-196">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="71b1f-197">Ниже приведен пример конфигурации для IdentityServer4, которая предполагает использование клиентов и ресурсов в памяти, предоставляемых пользовательским типом IClientStore.</span><span class="sxs-lookup"><span data-stu-id="71b1f-197">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a><span data-ttu-id="71b1f-198">Использование токенов безопасности</span><span class="sxs-lookup"><span data-stu-id="71b1f-198">Consume security tokens</span></span>

<span data-ttu-id="71b1f-199">Проверка подлинности в конечной точке OpenID Connect или выпуск собственных токенов безопасности подходят для некоторых ситуаций.</span><span class="sxs-lookup"><span data-stu-id="71b1f-199">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="71b1f-200">Но что если службе нужно просто предоставлять доступ только тем пользователям, у которых есть действительные токены безопасности, предоставленные другой службой?</span><span class="sxs-lookup"><span data-stu-id="71b1f-200">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="71b1f-201">Для такого случая в пакете **Microsoft.AspNetCore.Authentication.JwtBearer** доступно ПО промежуточного слоя, обрабатывающее токены JWT.</span><span class="sxs-lookup"><span data-stu-id="71b1f-201">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="71b1f-202">JWT расшифровывается как [JSON Web Token](https://tools.ietf.org/html/rfc7519) (веб-токен JSON). Это распространенный формат токенов безопасности (определенный в документе RFC 7519) для передачи утверждений безопасности.</span><span class="sxs-lookup"><span data-stu-id="71b1f-202">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="71b1f-203">Упрощенный пример использования ПО промежуточного слоя для применения таких токенов показан в следующем фрагменте кода, взятом из микрослужбы Ordering.Api в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="71b1f-203">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="71b1f-204">В примере используются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="71b1f-204">The parameters in this usage are:</span></span>

- <span data-ttu-id="71b1f-205">`Audience` представляет получателя входящего токена или ресурса, к которому токен предоставляет доступ.</span><span class="sxs-lookup"><span data-stu-id="71b1f-205">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="71b1f-206">Если значение этого параметра не совпадает со значением параметра в токене, токен будет отклонен.</span><span class="sxs-lookup"><span data-stu-id="71b1f-206">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="71b1f-207">`Authority` — это адрес сервера проверки подлинности, выпускающего токен.</span><span class="sxs-lookup"><span data-stu-id="71b1f-207">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="71b1f-208">ПО промежуточного слоя для проверки подлинности носителя JWT использует этот универсальный код ресурса (URI) для получения открытого ключа, с помощью которого можно проверить подпись токена.</span><span class="sxs-lookup"><span data-stu-id="71b1f-208">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="71b1f-209">ПО промежуточного слоя также проверяет, совпадает ли значение параметра `iss` в токене с этим кодом URI.</span><span class="sxs-lookup"><span data-stu-id="71b1f-209">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="71b1f-210">Другой параметр, `RequireHttpsMetadata`, полезен для тестирования. Присвоив ему значение false (ложь), можно проводить тестирование в средах, где у вас нет сертификатов.</span><span class="sxs-lookup"><span data-stu-id="71b1f-210">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="71b1f-211">В реальных развертываниях токены носителя JWT следует передавать только по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="71b1f-211">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="71b1f-212">При наличии этого ПО промежуточного слоя токены JWT автоматически извлекаются из заголовков авторизации.</span><span class="sxs-lookup"><span data-stu-id="71b1f-212">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="71b1f-213">Затем они десериализируются, проверяются (на основе значений параметров `Audience` и `Authority`) и сохраняются как сведения о пользователе для последующего применения в действиях MVC или фильтрах авторизации.</span><span class="sxs-lookup"><span data-stu-id="71b1f-213">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="71b1f-214">ПО промежуточного слоя для проверки подлинности носителя JWT может поддерживать и более сложные сценарии, например проверку токена с помощью локального сертификата, если центр сертификации недоступен.</span><span class="sxs-lookup"><span data-stu-id="71b1f-214">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="71b1f-215">В этом сценарии вы можете указать объект `TokenValidationParameters` в объекте `JwtBearerOptions`.</span><span class="sxs-lookup"><span data-stu-id="71b1f-215">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71b1f-216">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="71b1f-216">Additional resources</span></span>

- <span data-ttu-id="71b1f-217">**Совместное использование файлов cookie в приложениях** </span><span class="sxs-lookup"><span data-stu-id="71b1f-217">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="71b1f-218">**Общие сведения об Identity** </span><span class="sxs-lookup"><span data-stu-id="71b1f-218">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="71b1f-219">**Рик Андерсон (Rick Anderson). Двухфакторная проверка подлинности с помощью SMS** </span><span class="sxs-lookup"><span data-stu-id="71b1f-219">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="71b1f-220">**Проверка подлинности Facebook, Google и других внешних поставщиков** </span><span class="sxs-lookup"><span data-stu-id="71b1f-220">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="71b1f-221">**Мичелл Аникас (Michell Anicas). An Introduction to OAuth 2 (Введение в OAuth 2)**  </span><span class="sxs-lookup"><span data-stu-id="71b1f-221">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="71b1f-222">**репозиторий GitHub для поставщиков OAuth в ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="71b1f-222">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="71b1f-223">**Дэнни Строкис (Danny Strockis). Integrating Azure AD into an ASP.NET Core Web App (Интеграция Azure AD в веб-приложение ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="71b1f-223">**Danny Strockis. Integrating Azure AD into an ASP.NET Core web app** </span></span>\
  <https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/>

- <span data-ttu-id="71b1f-224">**IdentityServer4. Официальная документация** </span><span class="sxs-lookup"><span data-stu-id="71b1f-224">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="71b1f-225">[Назад](../implement-resilient-applications/monitor-app-health.md)
>[Вперед](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="71b1f-225">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
