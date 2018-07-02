---
title: Обеспечение безопасности веб-приложений и микрослужб .NET
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Обеспечение безопасности веб-приложений и микрослужб .NET
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ccdf6ecc30979e953d42a403c2c988780394df96
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106701"
---
# <a name="securing-net-microservices-and-web-applications"></a>Обеспечение безопасности веб-приложений и микрослужб .NET

Доступ к ресурсам и интерфейсам API, предоставляемым службой, часто требуется ограничить определенным кругом надежных пользователей или клиентов. Первый этап принятия подобных решений о доверии на уровне API — проверка подлинности. Проверка подлинности — это процесс достоверного установления личности пользователя.

При использовании микрослужб управление проверкой подлинности обычно осуществляется централизованно. Если имеется шлюз API, проверку подлинности целесообразно проводить в нем, как показано на рис. 11-1. При таком подходе отдельные микрослужбы не должны быть доступны напрямую (в обход шлюза API), если только не реализованы дополнительные средства безопасности для проверки того, поступают ли сообщения из шлюза или нет.

![](./media/image1.png)

**Рис. 11-1**. Централизованная проверка подлинности с помощью шлюза API

Если службы доступны напрямую, для проверки подлинности пользователей можно применять службу проверки подлинности, например Azure Active Directory или выделенную микрослужбу проверки подлинности, выступающую в роли службы токенов безопасности (STS). Сведения о доверии передаются между службами с помощью токенов безопасности или файлов cookie. (При необходимости они могут передаваться между приложениями в ASP.NET Core с помощью [служб защиты данных](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications).) Эта схема проиллюстрирована на рис. 11-2.

![](./media/image2.png)

**Рис. 11-2**. Проверка подлинности с помощью микрослужбы удостоверений; сведения о доверии передаются посредством токена авторизации

## <a name="authenticating-using-aspnet-core-identity"></a>Проверка подлинности с помощью удостоверения ASP.NET Core

Основным механизмом для идентификации пользователей приложения в ASP.NET Core является система членства на основе [удостоверений ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity). В удостоверении ASP.NET Core хранятся сведения о пользователе (в том числе данные для входа, роли и утверждения). Само удостоверение находится в хранилище данных, которое настраивает разработчик. Как правило, хранилище удостоверений ASP.NET Core представляет собой хранилище Entity Framework, которое входит в состав пакета Microsoft.AspNetCore.Identity.EntityFrameworkCore. Но вы также можете использовать пользовательские хранилища или пакеты сторонних поставщиков для хранения данных удостоверений в Хранилище таблиц Azure, DocumentDB или других системах.

Приведенный ниже код взят из шаблона проекта веб-приложения ASP.NET Core с выбранной проверкой подлинности отдельной учетной записи пользователя. В нем показано, как настроить удостоверение ASP.NET Core с помощью EntityFramework.Core в методе Startup.ConfigureServices.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

После настройки удостоверения ASP.NET Core его необходимо включить, вызвав app.UseIdentity в методе Startup.Configure службы.

Использование удостоверения ASP.NET Code обеспечивает несколько сценариев.

-   Создание сведений о пользователе с помощью типа UserManager (userManager.CreateAsync).

-   Проверка подлинности пользователей с помощью типа SignInManager. Вы можете использовать signInManager.SignInAsync для входа напрямую или signInManager.PasswordSignInAsync для проверки правильности пароля пользователя и выполнения его входа в систему.

-   Идентификация пользователя в соответствии со сведениями в файле cookie (которые считываются с помощью ПО промежуточного слоя удостоверения ASP.NET Core). Это позволяет включать в последующие запросы из браузера подписанное удостоверение и утверждения пользователя.

Удостоверение ASP.NET Core также поддерживает [двухфакторную проверку подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).

Для сценариев проверки подлинности, в которых используется локальное хранилище данных пользователей и удостоверения сохраняются между запросами с помощью файлов cookie (как обычно бывает в случае с веб-приложениями MVC), удостоверение ASP.NET Core является рекомендуемым решением.

## <a name="authenticating-using-external-providers"></a>Проверка подлинности с помощью внешних поставщиков

ASP.NET Core также поддерживает использование [внешних поставщиков проверки подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/social/) для обеспечения входа пользователей посредством потоков [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Это означает, что пользователи могут выполнять вход с помощью существующих процедур проверки подлинности, предоставляемых такими поставщиками, как Майкрософт, Google, Facebook или Twitter, и связывать свои удостоверения с удостоверением ASP.NET Core в приложении.

Для применения внешней проверки подлинности необходимо включить соответствующее ПО промежуточного слоя в конвейер обработки HTTP-запросов приложения. Это ПО промежуточного слоя отвечает за обработку запросов с целью получения маршрутов URI от поставщика проверки подлинности, регистрацию сведений об удостоверениях и предоставление доступа к ним посредством метода SignInManager.GetExternalLoginInfo.

Ниже перечислены популярные внешние поставщики проверки подлинности и связанные с ними пакеты NuGet.

**Майкрософт:** Microsoft.AspNetCore.Authentication.MicrosoftAccount

**Google:** Microsoft.AspNetCore.Authentication.Google

**Facebook:** Microsoft.AspNetCore.Authentication.Facebook

**Twitter:** Microsoft.AspNetCore.Authentication.Twitter

Во всех случаях ПО промежуточного слоя регистрируется посредством вызова метода регистрации, аналогичного методу app.Use{ExternalProvider}Authentication в Startup.Configure. Методы регистрации принимают объект параметров, который содержит идентификатор приложения и секретные данные (например пароль), необходимые поставщику. Чтобы внешние поставщики проверки подлинности могли сообщать пользователю, какое приложение запрашивает доступ к его удостоверению, приложение должно быть зарегистрировано (как описано в [документации по ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)).

После регистрации ПО промежуточного слоя в Startup.Configure можно предлагать пользователям выполнить вход при совершении любого действия контроллера. Для этого нужно создать объект AuthenticationProperties, который содержит имя и URL-адрес перенаправления поставщика проверки подлинности. После этого возвращается ответ на запрос, в котором передается объект AuthenticationProperties. В приведенном ниже коде показан пример.

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

Параметр redirectUrl содержит URL-адрес, на который внешний поставщик должен выполнить перенаправление после прохождения пользователем проверки подлинности. URL-адрес должен представлять действие, посредством которого будет выполнен вход пользователя на основании данных внешнего удостоверения, как показано в следующем упрощенном примере.

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

Если при создании проекта веб-приложения ASP.NET Code в Visual Studio был выбран вариант проверки подлинности **Отдельная учетная запись пользователя**, весь код, необходимый для входа посредством внешнего поставщика, уже имеется в проекте, как показано на рис. 11-3.

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

**Рис. 11-3**. Выбор способа внешней проверки подлинности при создании проекта веб-приложения

Помимо перечисленных выше внешних поставщиков проверки подлинности, доступны пакеты сторонних производителей, предоставляющие ПО промежуточного слоя для использования множества других внешних поставщиков проверки подлинности. Список см. в репозитории [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) в GitHub.

Естественно, можно создать и собственное ПО промежуточного слоя для внешней проверки подлинности.

## <a name="authenticating-with-bearer-tokens"></a>Проверка подлинности с помощью токенов носителя

Проверка подлинности посредством удостоверения ASP.NET Core (или посредством удостоверения и внешних поставщиков проверки подлинности) подходит для многих веб-приложений, позволяющих хранить сведения о пользователе в файле cookie. Но в других ситуациях хранить и передавать данные в файлах cookie нецелесообразно.

Например, в веб-API ASP.NET Core, предоставляющем конечные точки с поддержкой REST, к которым могут обращаться одностраничные приложения, собственные клиенты или даже другие веб-интерфейсы API, как правило, желательно использовать проверку подлинности посредством токена носителя. Такие приложения не работают с файлами cookie, но могут легко извлекать токен носителя и включать его в заголовок авторизации последующих запросов. Для проверки подлинности на основе токенов ASP.NET Core поддерживает несколько способов использования [OAuth 2.0](https://oauth.net/2/) и [OpenID Connect](https://openid.net/connect/).

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a>Проверка подлинности с помощью поставщика удостоверений OpenID Connect или OAuth 2.0

Если сведения о пользователе хранятся в Azure Active Directory или другом решении для управления удостоверениями, поддерживающем OpenID Connect или OAuth 2.0, вы можете использовать пакет Microsoft.AspNetCore.Authentication.OpenIdConnect для проверки подлинности с помощью рабочего процесса OpenID Connect. Например, для [проверки подлинности в Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/) веб-приложение ASP.NET Core может использовать ПО промежуточного слоя из этого пакета, как показано в следующем примере.

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

Значения конфигурации — это значения в Azure Active Directory, которые создаются при [регистрации приложения в качестве клиента Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad). Один идентификатор клиента может использоваться несколькими микрослужбами в приложении, если им все требуется выполнять проверку подлинности пользователей посредством Azure Active Directory.

Обратите внимание, что при использовании этого рабочего процесса ПО промежуточного слоя удостоверения ASP.NET Core не требуется, так как за хранение сведений о пользователях и проверку подлинности полностью отвечает Azure Active Directory.

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a>Выпуск токенов безопасности службой ASP.NET Core

Если вы предпочитаете выпускать токены безопасности для локальных пользователей удостоверения ASP.NET Core, а не использовать внешний поставщик удостоверений, то вы можете прибегнуть к ряду полезных библиотек сторонних разработчиков.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) и [OpenIddict](https://github.com/openiddict/openiddict-core) — это поставщики OpenID Connect, которые легко интегрируются с удостоверением ASP.NET Core и позволяют выпускать токены безопасности из службы ASP.NET Core. В [документации по IdentityServer4](https://identityserver4.readthedocs.io/en/release/) приведены подробные инструкции по работе с этой библиотекой. Ниже описываются основные действия по использованию IdentityServer4 для выпуска токенов.

1.  Вызовите app.UseIdentityServer в методе Startup.Configure, чтобы добавить IdentityServer4 в конвейер обработки HTTP-запросов приложения. Это позволит библиотеке обрабатывать запросы к конечным точкам OpenID Connect и OAuth2 как /connect/token.

2.  Настройте IdentityServer4 в методе Startup.ConfigureServices, выполнив вызов services.AddIdentityServer.

3.  Чтобы настроить сервер удостоверений, нужно предоставить следующие данные:

-   [учетные данные](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) для входа;

-   [ресурсы удостоверений и API](https://identityserver4.readthedocs.io/en/release/topics/resources.html), к которым пользователи могут запрашивать доступ:

<!-- -->

-   ресурсы API представляют защищенные данные или функциональные возможности, к которым пользователь может получать доступ с помощью токена доступа; примером ресурса API может служить веб-API (или набор веб-API), требующий авторизации;

-   ресурсы удостоверений представляют сведения (утверждения), которые предоставляются клиенту для идентификации пользователя; утверждения могут включать имя пользователя, адрес электронной почты и другие данные;

<!-- -->

-   [клиенты](https://identityserver4.readthedocs.io/en/release/topics/clients.html), которые будут подключаться для запроса токенов;

-   механизм хранения сведений о пользователях, например [удостоверение ASP.NET Core](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) или иной.

При указании клиентов и ресурсов, используемых IdentityServer4, можно передать коллекцию IEnumerable&lt;T&gt; соответствующего типа в методы, которые принимают хранилища клиентов или ресурсов в памяти. В более сложных сценариях типы клиентов или поставщиков ресурсов можно предоставлять с помощью внедрения зависимостей.

Ниже приведен пример конфигурации для IdentityServer4, которая предполагает использование клиентов и ресурсов в памяти, предоставляемых пользовательским типом IClientStore.

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a>Использование токенов безопасности

Проверка подлинности в конечной точке OpenID Connect или выпуск собственных токенов безопасности подходят для некоторых ситуаций. Но что если службе нужно просто предоставлять доступ только тем пользователям, у которых есть действительные токены безопасности, предоставленные другой службой?

Для такого случая в составе пакета Microsoft.AspNetCore.Authentication.JwtBearer доступно ПО промежуточного слоя, обрабатывающее токены JWT. JWT расшифровывается как [JSON Web Token](https://tools.ietf.org/html/rfc7519) (веб-токен JSON). Это распространенный формат токенов безопасности (определенный в документе RFC 7519) для передачи утверждений безопасности. Ниже приведен простой пример использования таких токенов с помощью ПО промежуточного слоя. Этот код должен предшествовать вызовам ПО промежуточного слоя MVC ASP.NET Core (app.UseMvc).

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

В примере используются следующие параметры.

-   Audience представляет получателя входящего токена или ресурса, к которому токен предоставляет доступ. Если значение этого параметра не совпадает со значением параметра aud в токене, токен будет отклонен.

-   Authority — это адрес сервера проверки подлинности, выпустившего токен. ПО промежуточного слоя для проверки подлинности носителя JWT использует этот универсальный код ресурса (URI) для получения открытого ключа, с помощью которого можно проверить подпись токена. ПО промежуточного слоя также проверяет, совпадает ли значение параметра iss в токене с этим кодом URI.

-   AutomaticAuthenticate — это логическое значение, которое указывает, должен ли пользователь, определяемый токеном, входить в систему автоматически.

Еще один параметр, RequireHttpsMetadata, в этом примере не используется. Он полезен для тестирования. Присвоив ему значение false, можно проводить тестирование в средах, в которых нет сертификатов. В реальных развертываниях токены носителя JWT следует передавать только по протоколу HTTPS.

При наличии этого ПО промежуточного слоя токены JWT автоматически извлекаются из заголовков авторизации. Затем они десериализуются, проверяются (на основе значений параметров Audience и Authority) и сохраняются как сведения о пользователе для дальнейшего использования действиями MVC или фильтрами авторизации.

ПО промежуточного слоя для проверки подлинности носителя JWT может поддерживать и более сложные сценарии, например проверку токена с помощью локального сертификата, если центр сертификации недоступен. В этом случае можно задать объект TokenValidationParameters в объекте JwtBearerOptions.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Совместное использование файлов cookie в приложениях**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)

-   **Общие сведения об Identity**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Рик Андерсон (Rick Anderson). Двухфакторная проверка подлинности с помощью SMS**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)

-   **Проверка подлинности Facebook, Google и других внешних поставщиков**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)

-   **Мичелл Аникас (Michell Anicas). An Introduction to OAuth 2 (Введение в OAuth 2)**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

-   **AspNet.Security.OAuth.Providers** (репозиторий GitHub для поставщиков OAuth в ASP.NET)
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   **Дэнни Строкис (Danny Strockis). Integrating Azure AD into an ASP.NET Core Web App (Интеграция Azure AD в веб-приложение ASP.NET Core)**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)

-   **IdentityServer4. Официальная документация**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)


>[!div class="step-by-step"]
[Назад](../implement-resilient-applications/monitor-app-health.md)
[Вперед](authorization-net-microservices-web-applications.md)
