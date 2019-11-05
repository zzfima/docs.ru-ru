---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198545"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>Авторизация: Требование нового метода для реализаций IAuthorizationPolicyProvider

В ASP.NET Core 3.0 в `IAuthorizationPolicyProvider` был добавлен новый метод `GetFallbackPolicyAsync`. Эта политика отката используется ПО промежуточного слоя для авторизации, если не указана другая политика.

Подробную информацию см. на странице [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Реализации `IAuthorizationPolicyProvider` не требовали метод `GetFallbackPolicyAsync`.

#### <a name="new-behavior"></a>Новое поведение

Реализации `IAuthorizationPolicyProvider` требуют метод `GetFallbackPolicyAsync`.

#### <a name="reason-for-change"></a>Причина изменения

Новый метод требуется для использования нового ПО `AuthorizationMiddleware`, если политика не указана.

#### <a name="recommended-action"></a>Рекомендуемое действие

Добавьте метод `GetFallbackPolicyAsync` в реализации `IAuthorizationPolicyProvider`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
