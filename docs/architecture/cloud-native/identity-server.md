---
title: IdentityServer для облачных приложений в машинном код
description: Создание архитектуры облачных приложений .NET для Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 48d0b95a40682f3127127851781b4d0e26e44630
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728578"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="12201-103">IdentityServer для собственных приложений в облаке</span><span class="sxs-lookup"><span data-stu-id="12201-103">IdentityServer for cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="12201-104">IdentityServer — это сервер проверки подлинности с открытым исходным кодом, который реализует стандарты OpenID Connect Connect (OIDC) и OAuth 2,0 для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="12201-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="12201-105">Он предназначен для предоставления общего способа проверки подлинности запросов ко всем приложениям независимо от того, являются ли они веб-приложениями, собственными, мобильными или интерфейсными конечными точками API.</span><span class="sxs-lookup"><span data-stu-id="12201-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="12201-106">IdentityServer можно использовать для реализации единого входа (SSO) для нескольких приложений и типов приложений.</span><span class="sxs-lookup"><span data-stu-id="12201-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="12201-107">Его можно использовать для проверки подлинности реальных пользователей с помощью форм входа и аналогичных пользовательских интерфейсов, а также для проверки подлинности на основе служб, которая обычно включает выдачу, проверку и обновление маркеров без какого-либо пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="12201-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="12201-108">IdentityServer разработана как настраиваемое решение.</span><span class="sxs-lookup"><span data-stu-id="12201-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="12201-109">Каждый экземпляр обычно настраивается в соответствии с потребностями конкретной организации и/или набора приложений.</span><span class="sxs-lookup"><span data-stu-id="12201-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="12201-110">Распространенные сценарии веб-приложений</span><span class="sxs-lookup"><span data-stu-id="12201-110">Common web app scenarios</span></span>

<span data-ttu-id="12201-111">Как правило, приложения должны поддерживать некоторые или все из следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="12201-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="12201-112">Пользователи, обращающиеся к веб-приложениям с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="12201-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="12201-113">Пользователи, обращающиеся к внутренним веб-API из приложений на основе браузера.</span><span class="sxs-lookup"><span data-stu-id="12201-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="12201-114">Пользователи мобильных и собственных клиентов, обращающихся к серверным веб-API.</span><span class="sxs-lookup"><span data-stu-id="12201-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="12201-115">Другие приложения, обращающиеся к серверным веб-API (без активного пользователя или пользовательского интерфейса).</span><span class="sxs-lookup"><span data-stu-id="12201-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="12201-116">Любому приложению может потребоваться взаимодействовать с другими веб-API, используя собственное удостоверение или делегируя идентификатору пользователя.</span><span class="sxs-lookup"><span data-stu-id="12201-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

<span data-ttu-id="12201-117">![типов и сценариев приложений](./media/application-types.png)
**рис. 8-1**.</span><span class="sxs-lookup"><span data-stu-id="12201-117">![Application types and scenarios](./media/application-types.png)
**Figure 8-1**.</span></span> <span data-ttu-id="12201-118">Типы приложений и сценарии.</span><span class="sxs-lookup"><span data-stu-id="12201-118">Application types and scenarios.</span></span>

<span data-ttu-id="12201-119">В каждом из этих сценариев предоставленная функциональность должна быть защищена от несанкционированного использования.</span><span class="sxs-lookup"><span data-stu-id="12201-119">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="12201-120">Как минимум, обычно требуется проверка подлинности пользователя или участника, выполняющего запрос ресурса.</span><span class="sxs-lookup"><span data-stu-id="12201-120">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="12201-121">Эта проверка подлинности может использовать один из нескольких распространенных протоколов, таких как SAML2p, WS-подача или OpenID Connect Connect.</span><span class="sxs-lookup"><span data-stu-id="12201-121">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="12201-122">Взаимодействие с API обычно использует протокол OAuth2 и его поддержку для маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="12201-122">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="12201-123">Отделение этих критических проблем безопасности и их реализация от самих приложений обеспечивает согласованность и повышает безопасность и удобство обслуживания.</span><span class="sxs-lookup"><span data-stu-id="12201-123">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="12201-124">Аутсорсинг этих задач на выделенный продукт, такой как IdentityServer, позволяет каждому приложению решить эти проблемы самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="12201-124">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="12201-125">IdentityServer предоставляет по промежуточного слоя, которое выполняется в приложении ASP.NET Core и добавляет поддержку OpenID Connect Connect и OAuth2 (см. [Поддерживаемые спецификации](http://docs.identityserver.io/en/latest/intro/specs.html)).</span><span class="sxs-lookup"><span data-stu-id="12201-125">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](http://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="12201-126">Организации создают собственное ASP.NET Core приложение с помощью по промежуточного слоя IdentityServer, которое действует как STS для всех своих протоколов безопасности на основе маркеров.</span><span class="sxs-lookup"><span data-stu-id="12201-126">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="12201-127">По промежуточного слоя IdentityServer предоставляет конечные точки для поддержки стандартных функций, в том числе:</span><span class="sxs-lookup"><span data-stu-id="12201-127">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="12201-128">Авторизация (проверка подлинности конечного пользователя)</span><span class="sxs-lookup"><span data-stu-id="12201-128">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="12201-129">Токен (запрос маркера программным путем)</span><span class="sxs-lookup"><span data-stu-id="12201-129">Token (request a token programmatically)</span></span>
- <span data-ttu-id="12201-130">Обнаружение (метаданные о сервере)</span><span class="sxs-lookup"><span data-stu-id="12201-130">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="12201-131">Сведения о пользователе (получение сведений о пользователе с действительным маркером доступа)</span><span class="sxs-lookup"><span data-stu-id="12201-131">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="12201-132">Авторизация устройства (используется для запуска авторизации потока устройства)</span><span class="sxs-lookup"><span data-stu-id="12201-132">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="12201-133">Самоанализ (проверка маркера)</span><span class="sxs-lookup"><span data-stu-id="12201-133">Introspection (token validation)</span></span>
- <span data-ttu-id="12201-134">Отзыв (отзыв маркера)</span><span class="sxs-lookup"><span data-stu-id="12201-134">Revocation (token revocation)</span></span>
- <span data-ttu-id="12201-135">Завершение сеанса (активация единого выхода для всех приложений)</span><span class="sxs-lookup"><span data-stu-id="12201-135">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="12201-136">Начало работы</span><span class="sxs-lookup"><span data-stu-id="12201-136">Getting started</span></span>

<span data-ttu-id="12201-137">IdentityServer4 является открытым исходным кодом и может использоваться бесплатно.</span><span class="sxs-lookup"><span data-stu-id="12201-137">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="12201-138">Его можно добавить в приложения с помощью пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="12201-138">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="12201-139">Основной пакет — [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) , который был загружен более 4 000 000 раз.</span><span class="sxs-lookup"><span data-stu-id="12201-139">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="12201-140">Базовый пакет не включает код пользовательского интерфейса и поддерживает только в конфигурации памяти.</span><span class="sxs-lookup"><span data-stu-id="12201-140">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="12201-141">Чтобы использовать ее с базой данных, вам также понадобится поставщик данных, такой как [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) , который использует Entity Framework Core для хранения конфигурации и рабочих данных для IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="12201-141">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="12201-142">Для пользовательского интерфейса можно скопировать файлы из [репозитория пользовательского интерфейса](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) быстрого запуска в приложение ASP.NET Core MVC, чтобы добавить поддержку входа и выхода с помощью по промежуточного слоя IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="12201-142">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="12201-143">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="12201-143">Configuration</span></span>

<span data-ttu-id="12201-144">IdentityServer поддерживает различные типы протоколов и поставщиков проверки подлинности, которые можно настроить в рамках каждой выборочной установки.</span><span class="sxs-lookup"><span data-stu-id="12201-144">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="12201-145">Обычно это делается в `Startup`ном классе ASP.NET Core приложения в методе `ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="12201-145">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="12201-146">Конфигурация включает в себя указание поддерживаемых протоколов и пути к серверам и конечным точкам, которые будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="12201-146">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="12201-147">На рис. 8-2 показан пример конфигурации, взятой из проекта пользовательского интерфейса быстрого запуска IdentityServer4:</span><span class="sxs-lookup"><span data-stu-id="12201-147">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="12201-148">**Рис. 8-2**.</span><span class="sxs-lookup"><span data-stu-id="12201-148">**Figure 8-2**.</span></span> <span data-ttu-id="12201-149">Настройка IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="12201-149">Configuring IdentityServer.</span></span>

<span data-ttu-id="12201-150">IdentityServer также содержит общедоступный демонстрационный сайт, который можно использовать для тестирования различных протоколов и конфигураций.</span><span class="sxs-lookup"><span data-stu-id="12201-150">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="12201-151">Он расположен по адресу [https://demo.identityserver.io/](https://demo.identityserver.io/) и содержит сведения о настройке его поведения в зависимости от предоставленных `client_id`.</span><span class="sxs-lookup"><span data-stu-id="12201-151">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="12201-152">Клиенты JavaScript</span><span class="sxs-lookup"><span data-stu-id="12201-152">JavaScript clients</span></span>

<span data-ttu-id="12201-153">Многие облачные приложения используют API на стороне сервера и полнофункциональные клиентские приложения с одними страницами (одностраничные приложения) на внешнем интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="12201-153">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="12201-154">IdentityServer поставляется с [клиентом JavaScript](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) через NPM, который можно добавить в одностраничные приложения, чтобы разрешить им использовать IdentityServer для входа, выхода и проверки подлинности на основе маркеров для веб-API.</span><span class="sxs-lookup"><span data-stu-id="12201-154">IdentityServer ships a [JavaScript client](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="12201-155">Ссылки</span><span class="sxs-lookup"><span data-stu-id="12201-155">References</span></span>

- [<span data-ttu-id="12201-156">Документация по IdentityServer</span><span class="sxs-lookup"><span data-stu-id="12201-156">IdentityServer documentation</span></span>](http://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="12201-157">Типы приложений</span><span class="sxs-lookup"><span data-stu-id="12201-157">Application types</span></span>](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [<span data-ttu-id="12201-158">Клиент OIDC JavaScript</span><span class="sxs-lookup"><span data-stu-id="12201-158">JavaScript OIDC client</span></span>](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="12201-159">[Назад](azure-active-directory.md)
>[Вперед](security.md)</span><span class="sxs-lookup"><span data-stu-id="12201-159">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
