---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394012"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>Аутентификация. Изменение подписи OAuthHandler ExchangeCodeAsync

В ASP.NET Core 3.0 сигнатура `OAuthHandler.ExchangeCodeAsync` была изменена с:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

В:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Строки `code` и `redirectUri` передавались как отдельные аргументы.

#### <a name="new-behavior"></a>Новое поведение

`Code` и `RedirectUri` являются свойствами `OAuthCodeExchangeContext`, которые можно задать с помощью конструктора `OAuthCodeExchangeContext`. Новый тип `OAuthCodeExchangeContext` — это единственный аргумент, передаваемый в `OAuthHandler.ExchangeCodeAsync`.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение позволяет предоставлять дополнительные параметры без критических изменений. Создавать новые перегрузки `ExchangeCodeAsync` не нужно.

#### <a name="recommended-action"></a>Рекомендованное действие

Создайте `OAuthCodeExchangeContext` с соответствующими значениями `code` и `redirectUri`. Необходимо указать экземпляр <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>. Этот единственный `OAuthCodeExchangeContext` экземпляр можно передать в `OAuthHandler.ExchangeCodeAsync`, а не в несколько аргументов.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
