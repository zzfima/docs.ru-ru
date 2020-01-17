---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901907"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Авторизация. Требование нового метода для реализаций IAuthorizationPolicyProvider

В ASP.NET Core 3.0 в `IAuthorizationPolicyProvider` был добавлен новый метод `GetFallbackPolicyAsync`. Эта политика отката используется ПО промежуточного слоя для авторизации, если не указана другая политика.

Подробную информацию см. на странице [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Реализации `IAuthorizationPolicyProvider` не требовали метод `GetFallbackPolicyAsync`.

#### <a name="new-behavior"></a>Новое поведение

Реализации `IAuthorizationPolicyProvider` требуют метод `GetFallbackPolicyAsync`.

#### <a name="reason-for-change"></a>Причина изменения

Новый метод требуется для использования нового ПО `AuthorizationMiddleware`, если политика не указана.

#### <a name="recommended-action"></a>Рекомендованное действие

Добавьте метод `GetFallbackPolicyAsync` в реализации `IAuthorizationPolicyProvider`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
