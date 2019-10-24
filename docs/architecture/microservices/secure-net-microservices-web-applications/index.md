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
# <a name="make-secure-net-microservices-and-web-applications"></a>Обеспечение безопасности микрослужб и веб-приложений .NET

Существует так много аспектов безопасности микрослужб и веб-приложений, что эта тема может легко занять несколько книг, поэтому в этом разделе мы сосредоточимся на проверке подлинности, авторизации и секретах приложений.

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a>Внедрение проверки подлинности в микрослужбы и веб-приложения .NET

Доступ к ресурсам и API-интерфейсам, публикуемым службой, часто требуется ограничить определенным кругом надежных пользователей или клиентов. Первый этап принятия подобных решений о доверии на уровне API — проверка подлинности. Проверка подлинности — это процесс достоверного установления личности пользователя.

При использовании микрослужб управление проверкой подлинности обычно осуществляется централизованно. Если имеется шлюз API, проверку подлинности целесообразно проводить в нем, как показано на рис. 9-1. При таком подходе отдельные микрослужбы не должны быть доступны напрямую (в обход шлюза API), если только не реализованы дополнительные средства безопасности для проверки того, поступают ли сообщения из шлюза или нет.

![Когда шлюз API централизует проверку подлинности, он добавляет сведения о пользователе при переадресации запросов в микрослужбы.](./media/image1.png)

**Рис. 9-1**. Централизованная проверка подлинности с помощью шлюза API

Если службы доступны напрямую, для проверки подлинности пользователей можно применять службу проверки подлинности, например Azure Active Directory или выделенную микрослужбу проверки подлинности, выступающую в роли службы токенов безопасности (STS). Сведения о доверии передаются между службами с помощью токенов безопасности или файлов cookie. (При необходимости эти токены могут передаваться между приложениями ASP.NET Core путем реализации [совместного использования файлов cookie](/aspnet/core/security/cookie-sharing).) Такая схема проиллюстрирована на рис. 9-2.

![При прямом доступе к микрослужбам доверие, включающее проверку подлинности и авторизацию, обрабатывается общим для всех токеном безопасности, который выдает специализированная микрослужба.](./media/image2.png)

**Рис. 9-2**. Проверка подлинности с помощью микрослужбы удостоверений; сведения о доверии передаются посредством токена авторизации

### <a name="authenticate-with-aspnet-core-identity"></a>Проверка подлинности с помощью ASP.NET Core Identity

Основным механизмом для идентификации пользователей приложения в ASP.NET Core является система членства на основе [удостоверений ASP.NET Core](/aspnet/core/security/authentication/identity). В удостоверении ASP.NET Core хранятся сведения о пользователе (в том числе данные для входа, роли и утверждения). Само удостоверение находится в хранилище данных, которое настраивает разработчик. Как правило, хранилище данных ASP.NET Core Identity представляет собой хранилище Entity Framework, входящее в пакет `Microsoft.AspNetCore.Identity.EntityFrameworkCore`. Однако вы также можете использовать настраиваемые хранилища или пакеты сторонних поставщиков для хранения сведений удостоверений в Хранилище таблиц Azure, CosmosDB или других местах.

Приведенный ниже код взят из шаблона проекта веб-приложения ASP.NET Core с выбранной проверкой подлинности отдельной учетной записи пользователя. В нем показано, как настроить удостоверение ASP.NET Core с помощью EntityFramework.Core в методе Startup.ConfigureServices.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

После настройки службы ASP.NET Core Indentity ее необходимо включить, вызвав app.UseIdentity в методе службы `Startup.Configure`.

Использование удостоверения ASP.NET Core обеспечивает несколько сценариев.

- Создание сведений о пользователе с помощью типа UserManager (userManager.CreateAsync).

- Проверка подлинности пользователей с помощью типа SignInManager. Вы можете использовать `signInManager.SignInAsync` для входа напрямую или `signInManager.PasswordSignInAsync` для проверки пользовательского пароля и последующего входа.

- Идентификация пользователя в соответствии со сведениями в файле cookie (которые считываются с помощью ПО промежуточного слоя удостоверения ASP.NET Core). Это позволяет включать в последующие запросы из браузера подписанное удостоверение и утверждения пользователя.

Удостоверение ASP.NET Core также поддерживает [двухфакторную проверку подлинности](/aspnet/core/security/authentication/2fa).

Для сценариев проверки подлинности, в которых используется локальное хранилище данных пользователей и удостоверения сохраняются между запросами с помощью файлов cookie (как обычно бывает в случае с веб-приложениями MVC), удостоверение ASP.NET Core является рекомендуемым решением.

### <a name="authenticate-with-external-providers"></a>Проверка подлинности с помощью внешних поставщиков

ASP.NET Core также поддерживает использование [внешних поставщиков проверки подлинности](/aspnet/core/security/authentication/social/) для обеспечения входа пользователей посредством рабочих процессов [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Это означает, что пользователи могут выполнять вход с помощью существующих процедур проверки подлинности, предоставляемых такими поставщиками, как Майкрософт, Google, Facebook или Twitter, и связывать свои удостоверения с удостоверением ASP.NET Core в вашем приложении.

Для применения внешней проверки подлинности необходимо включить соответствующее ПО промежуточного слоя в конвейер обработки HTTP-запросов приложения. Это ПО промежуточного слоя отвечает за обработку запросов с целью получения маршрутов URI от поставщика проверки подлинности, регистрацию сведений об удостоверениях и предоставление доступа к ним посредством метода SignInManager.GetExternalLoginInfo.

В следующей таблице показаны популярные внешние поставщики проверки подлинности и связанные с ними пакеты NuGet:

| **Поставщик**  | **Пакет**                                          |
| ------------- | ---------------------------------------------------- |
| **Майкрософт** | **Microsoft.AspNetCore.Authentication.MicrosoftAccount** |
| **Google**    | **Microsoft.AspNetCore.Authentication.Google**           |
| **Facebook**  | **Microsoft.AspNetCore.Authentication.Facebook**         |
| **Twitter**   | **Microsoft.AspNetCore.Authentication.Twitter**          |

Во всех случаях ПО промежуточного слоя регистрируется через вызов метода регистрации, аналогично `app.Use{ExternalProvider}Authentication` в `Startup.Configure`. Методы регистрации принимают объект параметров, который содержит идентификатор приложения и секретные данные (например пароль), необходимые поставщику. Чтобы внешние поставщики проверки подлинности могли сообщать пользователю, какое приложение запрашивает доступ к его удостоверению, приложение должно быть зарегистрировано (как описано в [документации по ASP.NET Core](/aspnet/core/security/authentication/social/)).

После регистрации ПО промежуточного слоя в `Startup.Configure` вы можете запрашивать у пользователей вход в любом действии контроллера. Для этого нужно создать объект `AuthenticationProperties`, который содержит имя и URL-адрес перенаправления поставщика проверки подлинности. Затем нужно вернуть ответ на запрос и передать в нем объект `AuthenticationProperties`. В приведенном ниже коде показан пример.

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

Если при создании проекта веб-приложения ASP.NET Code в Visual Studio выбрать вариант проверки подлинности **Отдельная учетная запись пользователя**, то весь код, необходимый для входа через внешнего поставщика, уже будет доступен в проекте, как показано на рис. 9-3.

![Диалоговое окно для нового веб-приложения ASP.NET Core, в котором выделена кнопка изменения проверки подлинности.](./media/image3.png)

**Рис. 9-3**. Выбор способа внешней проверки подлинности при создании проекта веб-приложения

Помимо перечисленных выше внешних поставщиков проверки подлинности, доступны пакеты сторонних производителей, предоставляющие ПО промежуточного слоя для использования множества других внешних поставщиков проверки подлинности. Список см. в репозитории [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) в GitHub.

Вы также можете создать собственное ПО промежуточного слоя для внешней проверки подлинности, позволяющее решать какие-то особые задачи.

### <a name="authenticate-with-bearer-tokens"></a>Проверка подлинности с помощью токенов носителя

Проверка подлинности посредством удостоверения ASP.NET Core (или посредством удостоверения и внешних поставщиков проверки подлинности) подходит для многих веб-приложений, позволяющих хранить сведения о пользователе в файле cookie. Но в других ситуациях хранить и передавать данные в файлах cookie нецелесообразно.

Например, в веб-API ASP.NET Core, предоставляющем конечные точки с поддержкой REST, к которым могут обращаться одностраничные приложения, собственные клиенты или даже другие веб-интерфейсы API, как правило, желательно использовать проверку подлинности посредством токена носителя. Такие приложения не работают с файлами cookie, но могут легко извлекать токен носителя и включать его в заголовок авторизации последующих запросов. Для проверки подлинности на основе токенов ASP.NET Core поддерживает несколько способов использования [OAuth 2.0](https://oauth.net/2/) и [OpenID Connect](https://openid.net/connect/).

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a>Проверка подлинности с помощью поставщика удостоверений OpenID Connect или OAuth 2.0

Если сведения о пользователе хранятся в Azure Active Directory или другом решении для управления удостоверениями, поддерживающем OpenID Connect или OAuth 2.0, вы можете использовать пакет **Microsoft.AspNetCore.Authentication.OpenIdConnect** для проверки подлинности с помощью рабочего процесса OpenID Connect. Например, для проверки подлинности в микрослужбе Identity.Api из eShopOnContainers веб-приложение ASP.NET Core может использовать ПО промежуточного слоя из этого пакета, как показано в следующем упрощенном примере `Startup.cs`:

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

Обратите внимание, что при использовании этого рабочего процесса ПО промежуточного слоя ASP.NET Core Identity не требуется, так как за хранение сведений о пользователях и проверку подлинности полностью отвечает служба Identity.

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a>Выпуск токенов безопасности службой ASP.NET Core

Если вы предпочитаете выпускать токены безопасности для локальных пользователей удостоверения ASP.NET Core, а не использовать внешний поставщик удостоверений, то вы можете прибегнуть к ряду полезных библиотек сторонних разработчиков.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) и [OpenIddict](https://github.com/openiddict/openiddict-core) — это поставщики OpenID Connect, которые легко интегрируются с удостоверением ASP.NET Core и позволяют выпускать токены безопасности из службы ASP.NET Core. В [документации по IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) приведены подробные инструкции по работе с этой библиотекой. Ниже описываются основные действия по использованию IdentityServer4 для выпуска токенов.

1. Вызовите app.UseIdentityServer в методе Startup.Configure, чтобы добавить IdentityServer4 в конвейер обработки HTTP-запросов приложения. Это позволит библиотеке обрабатывать запросы к конечным точкам OpenID Connect и OAuth2 как /connect/token.

2. Настройте IdentityServer4 в методе Startup.ConfigureServices, выполнив вызов services.AddIdentityServer.

3. Чтобы настроить сервер удостоверений, нужно задать следующие данные:

   - [учетные данные](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) для входа;

   - [ресурсы удостоверений и API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html), к которым пользователи могут запрашивать доступ:

      - ресурсы API представляют защищенные данные или функциональные возможности, к которым пользователь может получать доступ с помощью токена доступа; примером ресурса API может служить веб-API (или набор веб-API), требующий авторизации;

      - ресурсы удостоверений представляют сведения (утверждения), которые предоставляются клиенту для идентификации пользователя; утверждения могут включать имя пользователя, адрес электронной почты и другие данные;

   - [клиенты](https://identityserver4.readthedocs.io/en/latest/topics/clients.html), которые будут подключаться для запроса токенов;

   - механизм хранения сведений о пользователях, например [удостоверение ASP.NET Core](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) или иной.

При указании клиентов и ресурсов, используемых IdentityServer4, вы можете передать коллекцию <xref:System.Collections.Generic.IEnumerable%601> соответствующего типа в методы, которые принимают хранилища клиентов или ресурсов в памяти. В более сложных сценариях типы клиентов или поставщиков ресурсов можно предоставлять с помощью внедрения зависимостей.

Ниже приведен пример конфигурации для IdentityServer4, которая предполагает использование клиентов и ресурсов в памяти, предоставляемых пользовательским типом IClientStore.

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a>Использование токенов безопасности

Проверка подлинности в конечной точке OpenID Connect или выпуск собственных токенов безопасности подходят для некоторых ситуаций. Но что если службе нужно просто предоставлять доступ только тем пользователям, у которых есть действительные токены безопасности, предоставленные другой службой?

Для такого случая в пакете **Microsoft.AspNetCore.Authentication.JwtBearer** доступно ПО промежуточного слоя, обрабатывающее токены JWT. JWT расшифровывается как [JSON Web Token](https://tools.ietf.org/html/rfc7519) (веб-токен JSON). Это распространенный формат токенов безопасности (определенный в документе RFC 7519) для передачи утверждений безопасности. Упрощенный пример использования ПО промежуточного слоя для применения таких токенов показан в следующем фрагменте кода, взятом из микрослужбы Ordering.Api в eShopOnContainers.

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

В примере используются следующие параметры.

- `Audience` представляет получателя входящего токена или ресурса, к которому токен предоставляет доступ. Если значение этого параметра не совпадает со значением параметра в токене, токен будет отклонен.

- `Authority` — это адрес сервера проверки подлинности, выпускающего токен. ПО промежуточного слоя для проверки подлинности носителя JWT использует этот универсальный код ресурса (URI) для получения открытого ключа, с помощью которого можно проверить подпись токена. ПО промежуточного слоя также проверяет, совпадает ли значение параметра `iss` в токене с этим кодом URI.

Другой параметр, `RequireHttpsMetadata`, полезен для тестирования. Присвоив ему значение false (ложь), можно проводить тестирование в средах, где у вас нет сертификатов. В реальных развертываниях токены носителя JWT следует передавать только по протоколу HTTPS.

При наличии этого ПО промежуточного слоя токены JWT автоматически извлекаются из заголовков авторизации. Затем они десериализируются, проверяются (на основе значений параметров `Audience` и `Authority`) и сохраняются как сведения о пользователе для последующего применения в действиях MVC или фильтрах авторизации.

ПО промежуточного слоя для проверки подлинности носителя JWT может поддерживать и более сложные сценарии, например проверку токена с помощью локального сертификата, если центр сертификации недоступен. В этом сценарии вы можете указать объект `TokenValidationParameters` в объекте `JwtBearerOptions`.

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Совместное использование файлов cookie в приложениях** \
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- **Общие сведения об Identity** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Рик Андерсон (Rick Anderson). Двухфакторная проверка подлинности с помощью SMS** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- **Проверка подлинности Facebook, Google и других внешних поставщиков** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- **Мичелл Аникас (Michell Anicas). An Introduction to OAuth 2 (Введение в OAuth 2)**  \
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- **репозиторий GitHub для поставщиков OAuth в ASP.NET**\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- **Дэнни Строкис (Danny Strockis). Integrating Azure AD into an ASP.NET Core Web App (Интеграция Azure AD в веб-приложение ASP.NET Core)**  \
  <https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/>

- **IdentityServer4. Официальная документация** \
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
>[Назад](../implement-resilient-applications/monitor-app-health.md)
>[Вперед](authorization-net-microservices-web-applications.md)
