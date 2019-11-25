---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393968"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>Проверка подлинности. Замена типов Newtonsoft.Json

В ASP.NET Core 3.0 типы `Newtonsoft.Json`, которые использовались в API проверки подлинности, заменены на типы `System.Text.Json`. Базовое использование пакетов проверки подлинности остается неизменным, за исключением следующих случаев:

* классы, производные от поставщиков OAuth, например от [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers);
* расширенные реализации манипуляций с утверждениями.

Подробную информацию см. на странице [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105). Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

В производных реализациях OAuth самым типичным вариантом является замена `JObject.Parse` на `JsonDocument.Parse` в переопределении `CreateTicketAsync`, как показано [здесь](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40). Объект `JsonDocument` реализует интерфейс `IDisposable`.

В следующем списке перечислены известные изменения:

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> превращается в `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`. Аналогичным образом изменяются все производные реализации `ClaimAction`;
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> превращается в `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`;
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> превращается в `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`;
- из <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> удален один старый конструктор, а во втором `JObject` заменено на `JsonElement`. Соответственно обновлены свойство `User` и метод `RunClaimActions`;
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> теперь принимает параметр с типом `JsonDocument` вместо `JObject`. Соответственно обновлено свойство `Response`. `OAuthTokenResponse` теперь является высвобождаемым, и его высвобождает `OAuthHandler`. Производные реализации OAuth, переопределяющие `ExchangeCodeAsync`, не должны высвобождать `JsonDocument` или `OAuthTokenResponse`;
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> стал `JsonDocument` вместо `JObject`;
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> стал `JsonElement` вместо `JObject`;
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> теперь принимает `JsonElement` вместо `JObject`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
