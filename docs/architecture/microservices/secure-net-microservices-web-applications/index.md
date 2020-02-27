---
title: Обеспечение безопасности веб-приложений и микрослужб .NET
description: Безопасность микрослужб и веб-приложений .NET — узнайте о способах проверки подлинности в веб-приложениях ASP.NET Core.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 0ac2591f8650e9f8cf29560735a9ec803d29ee4f
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628336"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="e698d-103">Обеспечение безопасности микрослужб и веб-приложений .NET</span><span class="sxs-lookup"><span data-stu-id="e698d-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="e698d-104">Существует так много аспектов безопасности микрослужб и веб-приложений, что эта тема может легко занять несколько книг, поэтому в этом разделе мы сосредоточимся на проверке подлинности, авторизации и секретах приложений.</span><span class="sxs-lookup"><span data-stu-id="e698d-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="e698d-105">Внедрение проверки подлинности в микрослужбы и веб-приложения .NET</span><span class="sxs-lookup"><span data-stu-id="e698d-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="e698d-106">Доступ к ресурсам и API-интерфейсам, публикуемым службой, часто требуется ограничить определенным кругом надежных пользователей или клиентов.</span><span class="sxs-lookup"><span data-stu-id="e698d-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="e698d-107">Первый этап принятия подобных решений о доверии на уровне API — проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="e698d-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="e698d-108">Проверка подлинности — это процесс достоверного установления личности пользователя.</span><span class="sxs-lookup"><span data-stu-id="e698d-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="e698d-109">При использовании микрослужб управление проверкой подлинности обычно осуществляется централизованно.</span><span class="sxs-lookup"><span data-stu-id="e698d-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="e698d-110">Если имеется шлюз API, проверку подлинности целесообразно проводить в нем, как показано на рис. 9-1.</span><span class="sxs-lookup"><span data-stu-id="e698d-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="e698d-111">При таком подходе отдельные микрослужбы не должны быть доступны напрямую (в обход шлюза API), если только не реализованы дополнительные средства безопасности для проверки того, поступают ли сообщения из шлюза или нет.</span><span class="sxs-lookup"><span data-stu-id="e698d-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Схема взаимодействия клиентского мобильного приложения с серверной частью.](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="e698d-113">**Рис. 9-1**.</span><span class="sxs-lookup"><span data-stu-id="e698d-113">**Figure 9-1**.</span></span> <span data-ttu-id="e698d-114">Централизованная проверка подлинности с помощью шлюза API</span><span class="sxs-lookup"><span data-stu-id="e698d-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="e698d-115">Когда шлюз API централизует проверку подлинности, он добавляет сведения о пользователе при переадресации запросов в микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="e698d-115">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="e698d-116">Если службы доступны напрямую, для проверки подлинности пользователей можно применять службу проверки подлинности, например Azure Active Directory или выделенную микрослужбу проверки подлинности, выступающую в роли службы токенов безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="e698d-116">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="e698d-117">Сведения о доверии передаются между службами с помощью токенов безопасности или файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="e698d-117">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="e698d-118">(При необходимости эти токены могут передаваться между приложениями ASP.NET Core путем реализации [совместного использования файлов cookie](/aspnet/core/security/cookie-sharing).) Такая схема проиллюстрирована на рис. 9-2.</span><span class="sxs-lookup"><span data-stu-id="e698d-118">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![Схема, показывающая проверку подлинности с помощью серверных микрослужб.](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="e698d-120">**Рис. 9-2**.</span><span class="sxs-lookup"><span data-stu-id="e698d-120">**Figure 9-2**.</span></span> <span data-ttu-id="e698d-121">Проверка подлинности с помощью микрослужбы удостоверений; сведения о доверии передаются посредством токена авторизации</span><span class="sxs-lookup"><span data-stu-id="e698d-121">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="e698d-122">При прямом доступе к микрослужбам доверие, включающее проверку подлинности и авторизацию, обрабатывается общим для всех токеном безопасности, который выдает специализированная микрослужба.</span><span class="sxs-lookup"><span data-stu-id="e698d-122">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="e698d-123">Проверка подлинности с помощью ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="e698d-123">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="e698d-124">Основным механизмом для идентификации пользователей приложения в ASP.NET Core является система членства на основе [удостоверений ASP.NET Core](/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="e698d-124">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="e698d-125">В удостоверении ASP.NET Core хранятся сведения о пользователе (в том числе данные для входа, роли и утверждения). Само удостоверение находится в хранилище данных, которое настраивает разработчик.</span><span class="sxs-lookup"><span data-stu-id="e698d-125">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="e698d-126">Как правило, хранилище данных ASP.NET Core Identity представляет собой хранилище Entity Framework, входящее в пакет `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="e698d-126">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="e698d-127">Однако вы также можете использовать настраиваемые хранилища или пакеты сторонних поставщиков для хранения сведений удостоверений в Хранилище таблиц Azure, CosmosDB или других местах.</span><span class="sxs-lookup"><span data-stu-id="e698d-127">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

> [!TIP]
> <span data-ttu-id="e698d-128">В ASP.NET Core 2.1 и более поздних версиях предоставляется [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) в виде [библиотеки классов Razor](/aspnet/core/razor-pages/ui-class), поэтому в проекте не будет отображаться большая часть необходимого кода, как в предыдущих версиях.</span><span class="sxs-lookup"><span data-stu-id="e698d-128">ASP.NET Core 2.1 and later provides [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) as a [Razor Class Library](/aspnet/core/razor-pages/ui-class), so you won't see much of the necessary code in your project, as was the case for previous versions.</span></span> <span data-ttu-id="e698d-129">Дополнительные сведения о том, как настроить код Identity в соответствии со своими требованиями, см. в статье [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity) (Шаблоны для использования Identity в проектах ASP.NET Core).</span><span class="sxs-lookup"><span data-stu-id="e698d-129">For details on how to customize the Identity code to suit your needs, see [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity).</span></span>

<span data-ttu-id="e698d-130">Приведенный ниже код взят из шаблона проекта веб-приложения ASP.NET Core MVC 3.1 с выбранной проверкой подлинности отдельной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e698d-130">The following code is taken from the ASP.NET Core Web Application MVC 3.1 project template with individual user account authentication selected.</span></span> <span data-ttu-id="e698d-131">В нем показано, как настроить ASP.NET Core Identity с помощью Entity Framework Core в методе `Startup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="e698d-131">It shows how to configure ASP.NET Core Identity using Entity Framework Core in the `Startup.ConfigureServices` method.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
    //...
}
```

<span data-ttu-id="e698d-132">После настройки системы ASP.NET Core Identity ее необходимо включить, добавив `app.UseAuthentication()` и `endpoints.MapRazorPages()` как показано в следующем коде в методе `Startup.Configure` службы.</span><span class="sxs-lookup"><span data-stu-id="e698d-132">Once ASP.NET Core Identity is configured, you enable it by adding the `app.UseAuthentication()` and `endpoints.MapRazorPages()` as shown in the following code in the service's `Startup.Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    //...
    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
    //...
}
```

> [!IMPORTANT]
> <span data-ttu-id="e698d-133">Для правильной работы Identity строки в приведенном выше коде **ДОЛЖНЫ ИСПОЛЬЗОВАТЬСЯ В ТАКОМ ЖЕ ПОРЯДКЕ**.</span><span class="sxs-lookup"><span data-stu-id="e698d-133">The lines in the preceeding code **MUST BE IN THE ORDER SHOWN** for Identity to work correctly.</span></span>

<span data-ttu-id="e698d-134">Использование удостоверения ASP.NET Core обеспечивает несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="e698d-134">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="e698d-135">Создание сведений о пользователе с помощью типа UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="e698d-135">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="e698d-136">Проверка подлинности пользователей с помощью типа SignInManager.</span><span class="sxs-lookup"><span data-stu-id="e698d-136">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="e698d-137">Вы можете использовать `signInManager.SignInAsync` для входа напрямую или `signInManager.PasswordSignInAsync` для проверки пользовательского пароля и последующего входа.</span><span class="sxs-lookup"><span data-stu-id="e698d-137">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="e698d-138">Идентификация пользователя в соответствии со сведениями в файле cookie (которые считываются с помощью ПО промежуточного слоя удостоверения ASP.NET Core). Это позволяет включать в последующие запросы из браузера подписанное удостоверение и утверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="e698d-138">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="e698d-139">Удостоверение ASP.NET Core также поддерживает [двухфакторную проверку подлинности](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="e698d-139">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="e698d-140">Для сценариев проверки подлинности, в которых используется локальное хранилище данных пользователей и удостоверения сохраняются между запросами с помощью файлов cookie (как обычно бывает в случае с веб-приложениями MVC), удостоверение ASP.NET Core является рекомендуемым решением.</span><span class="sxs-lookup"><span data-stu-id="e698d-140">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="e698d-141">Проверка подлинности с помощью внешних поставщиков</span><span class="sxs-lookup"><span data-stu-id="e698d-141">Authenticate with external providers</span></span>

<span data-ttu-id="e698d-142">ASP.NET Core также поддерживает использование [внешних поставщиков проверки подлинности](/aspnet/core/security/authentication/social/) для обеспечения входа пользователей посредством рабочих процессов [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="e698d-142">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="e698d-143">Это означает, что пользователи могут выполнять вход с помощью существующих процедур проверки подлинности, предоставляемых такими поставщиками, как Майкрософт, Google, Facebook или Twitter, и связывать свои удостоверения с удостоверением ASP.NET Core в вашем приложении.</span><span class="sxs-lookup"><span data-stu-id="e698d-143">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="e698d-144">Чтобы использовать внешнюю проверку подлинности (помимо промежуточного ПО для проверки подлинности), упомянутую ранее, с помощью метода `app.UseAuthentication()`, потребуется также зарегистрировать внешний поставщик в `Startup`, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e698d-144">To use external authentication, besides including the authentication middleware as mentioned before, using the `app.UseAuthentication()` method, you also have to register the external provider in `Startup` as shown in the following example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddAuthentication()
        .AddMicrosoftAccount(microsoftOptions =>
        {
            microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ClientId"];
            microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:ClientSecret"];
        })
        .AddGoogle(googleOptions => { ... })
        .AddTwitter(twitterOptions => { ... })
        .AddFacebook(facebookOptions => { ... });
    //...
}
```

<span data-ttu-id="e698d-145">В следующей таблице показаны популярные внешние поставщики проверки подлинности и связанные с ними пакеты NuGet:</span><span class="sxs-lookup"><span data-stu-id="e698d-145">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="e698d-146">**Поставщик**</span><span class="sxs-lookup"><span data-stu-id="e698d-146">**Provider**</span></span>  | <span data-ttu-id="e698d-147">**Пакет**</span><span class="sxs-lookup"><span data-stu-id="e698d-147">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="e698d-148">**Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="e698d-148">**Microsoft**</span></span> | <span data-ttu-id="e698d-149">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="e698d-149">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="e698d-150">**Google**</span><span class="sxs-lookup"><span data-stu-id="e698d-150">**Google**</span></span>    | <span data-ttu-id="e698d-151">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="e698d-151">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="e698d-152">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="e698d-152">**Facebook**</span></span>  | <span data-ttu-id="e698d-153">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="e698d-153">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="e698d-154">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="e698d-154">**Twitter**</span></span>   | <span data-ttu-id="e698d-155">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="e698d-155">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="e698d-156">Во всех случаях необходимо выполнить процедуру регистрации приложения, которая зависит от поставщика и обычно включает в себя такие задачи:</span><span class="sxs-lookup"><span data-stu-id="e698d-156">In all cases, you must complete an application registration procedure that is vendor dependent and that usually involves:</span></span>

1. <span data-ttu-id="e698d-157">Получение идентификатора клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="e698d-157">Getting a Client Application ID.</span></span>
2. <span data-ttu-id="e698d-158">Получение секрета клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="e698d-158">Getting a Client Application Secret.</span></span>
3. <span data-ttu-id="e698d-159">Настройка URL-адреса перенаправления, который обрабатывается ПО промежуточного слоя авторизации и зарегистрированным поставщиком.</span><span class="sxs-lookup"><span data-stu-id="e698d-159">Configuring an redirection URL, that's handled by the authorization middleware and the registered provider</span></span>
4. <span data-ttu-id="e698d-160">(Необязательно) Настройка URL-адреса выхода для правильной обработки выхода в сценарии с использованием единого входа.</span><span class="sxs-lookup"><span data-stu-id="e698d-160">Optionally, configuring a sign-out URL to properly handle sign out in a Single Sign On (SSO) scenario.</span></span>

<span data-ttu-id="e698d-161">Дополнительные сведения о настройке приложения для внешнего поставщика см. в документации ASP.NET Core по [внешнему поставщику проверки подлинности](/aspnet/core/security/authentication/social/).</span><span class="sxs-lookup"><span data-stu-id="e698d-161">For details on configuring your app for an external provider, see the [External provider authentication in the ASP.NET Core documentation](/aspnet/core/security/authentication/social/)).</span></span>

>[!TIP]
><span data-ttu-id="e698d-162">Все данные обрабатываются с помощью ПО промежуточного слоя авторизации и ранее упомянутых служб.</span><span class="sxs-lookup"><span data-stu-id="e698d-162">All details are handled by the authorization middleware and services previously mentioned.</span></span> <span data-ttu-id="e698d-163">Поэтому при создании проекта веб-приложения ASP.NET Code в Visual Studio нужно лишь выбрать вариант проверки подлинности **Отдельная учетная запись пользователя** (помимо регистрации поставщиков проверки подлинности, упомянутых ранее), как показано на рис. 9-3.</span><span class="sxs-lookup"><span data-stu-id="e698d-163">So, you just have to choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, as shown in Figure 9-3, besides registering the authentication providers previously mentioned.</span></span>

![Снимок экрана: диалоговое окно "Создать веб-приложение ASP.NET Core".](./media/index/select-individual-user-account-authentication-option.png)

<span data-ttu-id="e698d-165">**Рис. 9-3**.</span><span class="sxs-lookup"><span data-stu-id="e698d-165">**Figure 9-3**.</span></span> <span data-ttu-id="e698d-166">Выбор варианта "Отдельная учетная запись пользователя" для использования внешней проверки подлинности при создании проекта веб-приложения в Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="e698d-166">Selecting the Individual User Accounts option, for using external authentication, when creating a web application project in Visual Studio 2019.</span></span>

<span data-ttu-id="e698d-167">Помимо перечисленных выше внешних поставщиков проверки подлинности, доступны пакеты сторонних производителей, предоставляющие ПО промежуточного слоя для использования множества других внешних поставщиков проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="e698d-167">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="e698d-168">Список см. в репозитории [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="e698d-168">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repository on GitHub.</span></span>

<span data-ttu-id="e698d-169">Вы также можете создать собственное ПО промежуточного слоя для внешней проверки подлинности, позволяющее решать какие-то особые задачи.</span><span class="sxs-lookup"><span data-stu-id="e698d-169">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="e698d-170">Проверка подлинности с помощью токенов носителя</span><span class="sxs-lookup"><span data-stu-id="e698d-170">Authenticate with bearer tokens</span></span>

<span data-ttu-id="e698d-171">Проверка подлинности посредством удостоверения ASP.NET Core (или посредством удостоверения и внешних поставщиков проверки подлинности) подходит для многих веб-приложений, позволяющих хранить сведения о пользователе в файле cookie.</span><span class="sxs-lookup"><span data-stu-id="e698d-171">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="e698d-172">Но в других ситуациях хранить и передавать данные в файлах cookie нецелесообразно.</span><span class="sxs-lookup"><span data-stu-id="e698d-172">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="e698d-173">Например, в веб-API ASP.NET Core, предоставляющем конечные точки с поддержкой REST, к которым могут обращаться одностраничные приложения, собственные клиенты или даже другие веб-интерфейсы API, как правило, желательно использовать проверку подлинности посредством токена носителя.</span><span class="sxs-lookup"><span data-stu-id="e698d-173">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="e698d-174">Такие приложения не работают с файлами cookie, но могут легко извлекать токен носителя и включать его в заголовок авторизации последующих запросов.</span><span class="sxs-lookup"><span data-stu-id="e698d-174">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="e698d-175">Для проверки подлинности на основе токенов ASP.NET Core поддерживает несколько способов использования [OAuth 2.0](https://oauth.net/2/) и [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="e698d-175">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="e698d-176">Проверка подлинности с помощью поставщика удостоверений OpenID Connect или OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="e698d-176">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="e698d-177">Если сведения о пользователе хранятся в Azure Active Directory или другом решении для управления удостоверениями, поддерживающем OpenID Connect или OAuth 2.0, вы можете использовать пакет **Microsoft.AspNetCore.Authentication.OpenIdConnect** для проверки подлинности с помощью рабочего процесса OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="e698d-177">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="e698d-178">Например, для проверки подлинности в микрослужбе Identity.Api из eShopOnContainers веб-приложение ASP.NET Core может использовать ПО промежуточного слоя из этого пакета, как показано в следующем упрощенном примере `Startup.cs`:</span><span class="sxs-lookup"><span data-stu-id="e698d-178">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");
    var sessionCookieLifetime = configuration.GetValue("SessionCookieLifetimeMinutes", 60);

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
    })
    .AddCookie(setup => setup.ExpireTimeSpan = TimeSpan.FromMinutes(sessionCookieLifetime))
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl.ToString();
        options.SignedOutRedirectUri = callBackUrl.ToString();
        options.ClientId = useLoadTest ? "mvctest" : "mvc";
        options.ClientSecret = "secret";
        options.ResponseType = useLoadTest ? "code id_token token" : "code id_token";
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

<span data-ttu-id="e698d-179">Обратите внимание, что при использовании этого рабочего процесса ПО промежуточного слоя ASP.NET Core Identity не требуется, так как за хранение сведений о пользователях и проверку подлинности полностью отвечает служба Identity.</span><span class="sxs-lookup"><span data-stu-id="e698d-179">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="e698d-180">Выпуск токенов безопасности службой ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e698d-180">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="e698d-181">Если вы предпочитаете выпускать токены безопасности для локальных пользователей удостоверения ASP.NET Core, а не использовать внешний поставщик удостоверений, то вы можете прибегнуть к ряду полезных библиотек сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="e698d-181">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="e698d-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) и [OpenIddict](https://github.com/openiddict/openiddict-core) — это поставщики OpenID Connect, которые легко интегрируются с удостоверением ASP.NET Core и позволяют выпускать токены безопасности из службы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e698d-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="e698d-183">В [документации по IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) приведены подробные инструкции по работе с этой библиотекой.</span><span class="sxs-lookup"><span data-stu-id="e698d-183">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="e698d-184">Ниже описываются основные действия по использованию IdentityServer4 для выпуска токенов.</span><span class="sxs-lookup"><span data-stu-id="e698d-184">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="e698d-185">Вызовите app.UseIdentityServer в методе Startup.Configure, чтобы добавить IdentityServer4 в конвейер обработки HTTP-запросов приложения.</span><span class="sxs-lookup"><span data-stu-id="e698d-185">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="e698d-186">Это позволит библиотеке обрабатывать запросы к конечным точкам OpenID Connect и OAuth2 как /connect/token.</span><span class="sxs-lookup"><span data-stu-id="e698d-186">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="e698d-187">Настройте IdentityServer4 в методе Startup.ConfigureServices, выполнив вызов services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="e698d-187">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="e698d-188">Чтобы настроить сервер удостоверений, нужно задать следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e698d-188">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="e698d-189">[учетные данные](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) для входа;</span><span class="sxs-lookup"><span data-stu-id="e698d-189">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="e698d-190">[ресурсы удостоверений и API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html), к которым пользователи могут запрашивать доступ:</span><span class="sxs-lookup"><span data-stu-id="e698d-190">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="e698d-191">ресурсы API представляют защищенные данные или функциональные возможности, к которым пользователь может получать доступ с помощью токена доступа;</span><span class="sxs-lookup"><span data-stu-id="e698d-191">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="e698d-192">примером ресурса API может служить веб-API (или набор веб-API), требующий авторизации;</span><span class="sxs-lookup"><span data-stu-id="e698d-192">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="e698d-193">ресурсы удостоверений представляют сведения (утверждения), которые предоставляются клиенту для идентификации пользователя;</span><span class="sxs-lookup"><span data-stu-id="e698d-193">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="e698d-194">утверждения могут включать имя пользователя, адрес электронной почты и другие данные;</span><span class="sxs-lookup"><span data-stu-id="e698d-194">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="e698d-195">[клиенты](https://identityserver4.readthedocs.io/en/latest/topics/clients.html), которые будут подключаться для запроса токенов;</span><span class="sxs-lookup"><span data-stu-id="e698d-195">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="e698d-196">механизм хранения сведений о пользователях, например [удостоверение ASP.NET Core](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) или иной.</span><span class="sxs-lookup"><span data-stu-id="e698d-196">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="e698d-197">При указании клиентов и ресурсов, используемых IdentityServer4, вы можете передать коллекцию <xref:System.Collections.Generic.IEnumerable%601> соответствующего типа в методы, которые принимают хранилища клиентов или ресурсов в памяти.</span><span class="sxs-lookup"><span data-stu-id="e698d-197">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="e698d-198">В более сложных сценариях типы клиентов или поставщиков ресурсов можно предоставлять с помощью внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="e698d-198">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="e698d-199">Ниже приведен пример конфигурации для IdentityServer4, которая предполагает использование клиентов и ресурсов в памяти, предоставляемых пользовательским типом IClientStore.</span><span class="sxs-lookup"><span data-stu-id="e698d-199">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //...
    services.AddSingleton<IClientStore, CustomClientStore>();
    services.AddIdentityServer()
        .AddSigningCredential("CN=sts")
        .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
        .AddAspNetIdentity<ApplicationUser>();
    //...
}
```

### <a name="consume-security-tokens"></a><span data-ttu-id="e698d-200">Использование токенов безопасности</span><span class="sxs-lookup"><span data-stu-id="e698d-200">Consume security tokens</span></span>

<span data-ttu-id="e698d-201">Проверка подлинности в конечной точке OpenID Connect или выпуск собственных токенов безопасности подходят для некоторых ситуаций.</span><span class="sxs-lookup"><span data-stu-id="e698d-201">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="e698d-202">Но что если службе нужно просто предоставлять доступ только тем пользователям, у которых есть действительные токены безопасности, предоставленные другой службой?</span><span class="sxs-lookup"><span data-stu-id="e698d-202">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="e698d-203">Для такого случая в пакете **Microsoft.AspNetCore.Authentication.JwtBearer** доступно ПО промежуточного слоя, обрабатывающее токены JWT.</span><span class="sxs-lookup"><span data-stu-id="e698d-203">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="e698d-204">JWT расшифровывается как [JSON Web Token](https://tools.ietf.org/html/rfc7519) (веб-токен JSON). Это распространенный формат токенов безопасности (определенный в документе RFC 7519) для передачи утверждений безопасности.</span><span class="sxs-lookup"><span data-stu-id="e698d-204">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="e698d-205">Упрощенный пример использования ПО промежуточного слоя для применения таких токенов показан в следующем фрагменте кода, взятом из микрослужбы Ordering.Api в eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="e698d-205">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="e698d-206">В примере используются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e698d-206">The parameters in this usage are:</span></span>

- <span data-ttu-id="e698d-207">`Audience` представляет получателя входящего токена или ресурса, к которому токен предоставляет доступ.</span><span class="sxs-lookup"><span data-stu-id="e698d-207">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="e698d-208">Если значение этого параметра не совпадает со значением параметра в токене, токен будет отклонен.</span><span class="sxs-lookup"><span data-stu-id="e698d-208">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="e698d-209">`Authority` — это адрес сервера проверки подлинности, выпускающего токен.</span><span class="sxs-lookup"><span data-stu-id="e698d-209">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="e698d-210">ПО промежуточного слоя для проверки подлинности носителя JWT использует этот универсальный код ресурса (URI) для получения открытого ключа, с помощью которого можно проверить подпись токена.</span><span class="sxs-lookup"><span data-stu-id="e698d-210">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="e698d-211">ПО промежуточного слоя также проверяет, совпадает ли значение параметра `iss` в токене с этим кодом URI.</span><span class="sxs-lookup"><span data-stu-id="e698d-211">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="e698d-212">Другой параметр, `RequireHttpsMetadata`, полезен для тестирования. Присвоив ему значение false (ложь), можно проводить тестирование в средах, где у вас нет сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e698d-212">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="e698d-213">В реальных развертываниях токены носителя JWT следует передавать только по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e698d-213">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="e698d-214">При наличии этого ПО промежуточного слоя токены JWT автоматически извлекаются из заголовков авторизации.</span><span class="sxs-lookup"><span data-stu-id="e698d-214">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="e698d-215">Затем они десериализируются, проверяются (на основе значений параметров `Audience` и `Authority`) и сохраняются как сведения о пользователе для последующего применения в действиях MVC или фильтрах авторизации.</span><span class="sxs-lookup"><span data-stu-id="e698d-215">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="e698d-216">ПО промежуточного слоя для проверки подлинности носителя JWT может поддерживать и более сложные сценарии, например проверку токена с помощью локального сертификата, если центр сертификации недоступен.</span><span class="sxs-lookup"><span data-stu-id="e698d-216">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="e698d-217">В этом сценарии вы можете указать объект `TokenValidationParameters` в объекте `JwtBearerOptions`.</span><span class="sxs-lookup"><span data-stu-id="e698d-217">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e698d-218">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e698d-218">Additional resources</span></span>

- <span data-ttu-id="e698d-219">**Совместное использование файлов cookie в приложениях** </span><span class="sxs-lookup"><span data-stu-id="e698d-219">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="e698d-220">**Общие сведения об Identity** </span><span class="sxs-lookup"><span data-stu-id="e698d-220">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="e698d-221">**Рик Андерсон (Rick Anderson). Двухфакторная проверка подлинности с помощью SMS** </span><span class="sxs-lookup"><span data-stu-id="e698d-221">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="e698d-222">**Проверка подлинности Facebook, Google и других внешних поставщиков** </span><span class="sxs-lookup"><span data-stu-id="e698d-222">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="e698d-223">**Мичелл Аникас (Michell Anicas). An Introduction to OAuth 2 (Введение в OAuth 2)**  </span><span class="sxs-lookup"><span data-stu-id="e698d-223">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="e698d-224">**репозиторий GitHub для поставщиков OAuth в ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="e698d-224">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="e698d-225">**IdentityServer4. Официальная документация** </span><span class="sxs-lookup"><span data-stu-id="e698d-225">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="e698d-226">[Назад](../implement-resilient-applications/monitor-app-health.md)
>[Вперед](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="e698d-226">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
