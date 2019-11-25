---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394229"
---
### <a name="authentication-google-deprecated-and-replaced"></a>Проверка подлинности. Механизм Google+ устарел и заменяется

Google постепенно [отключает](https://developers.google.com/+/api-shutdown) механизм входа через Google+ для приложений, начиная с 28 января 2019 г.

#### <a name="change-description"></a>Описание изменений

Платформы ASP.NET 4.x и ASP.NET Core использовали API для входа, предоставленные Google+, для проверки подлинности пользователей с учетной записью Google в веб-приложениях. Это изменение затронет такие пакеты NuGet, как [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) для ASP.NET Core и [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) для `Microsoft.Owin` с ASP.NET Web Forms и MVC.

В API-интерфейсах, которые Google предоставил в качестве замены, используется другой источник данных и другой формат. Ниже описаны методы и решения, которые позволят учесть эти структурные изменения. Приложения должны проверять, соответствуют ли данные требованиям. Например, имена, адреса электронной почты, ссылки на профили и фотографии профилей могут возвращать немного другие значения, чем раньше.

#### <a name="version-introduced"></a>Представленная версия

Все версии. Это изменение является внешним по отношению к ASP.NET Core.

#### <a name="recommended-action"></a>Рекомендуемое действие

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>Owin с ASP.NET Web Forms и MVC

Для `Microsoft.Owin` версии 3.1.0 и более поздних [здесь](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) описаны меры для временного устранения рисков. Приложения должны по этой процедуре проверить наличие изменений в формате данных. Планируется выпуск версии `Microsoft.Owin` 4.0.1 с исправлением. Все приложения, которые используют любую из предыдущих версий, нужно обновить до версии 4.0.1.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1.x

Устранение рисков, описанное в инструкции для [Owin с ASP.NET Web Forms и MVC](#owin-with-aspnet-web-forms-and-mvc), можно адаптировать для ASP.NET Core 1. x. Исправления пакетов NuGet не планируются, так как версия 1.x уже достигла [завершения жизненного цикла](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2.x

Для `Microsoft.AspNetCore.Authentication.Google` версии 2.x замените существующий вызов `AddGoogle` в `Startup.ConfigureServices` следующим кодом:

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

В февральские обновления 2.1 и 2.2 описанное выше изменение конфигурации включено как новый вариант по умолчанию. Обновления для ASP.NET Core 2.0 не планируются, так как эта версия достигла [завершения жизненного цикла](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-30"></a>ASP.NET Core 3.0

Метод устранения рисков, предложенный для ASP.NET Core 2.x, также можно использовать и для ASP.NET Core 3.0. В будущих предварительных версиях для 3.0 пакет `Microsoft.AspNetCore.Authentication.Google` может быть удален. Вместо него пользователям будет предоставляться `Microsoft.AspNetCore.Authentication.OpenIdConnect`. В следующем примере кода показано, как заменить `AddGoogle` на `AddOpenIdConnect` в `Startup.ConfigureServices`. Эту замену можно использовать для ASP.NET Core 2.0 и более поздних версий, а также адаптировать для ASP.NET Core 1.x по необходимости.

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
