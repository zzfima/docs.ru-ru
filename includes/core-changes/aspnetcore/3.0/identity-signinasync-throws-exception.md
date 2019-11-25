---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394354"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>Удостоверение. Создание исключения SignInAsync для удостоверения, не прошедшего проверку подлинности

По умолчанию `SignInAsync` создает исключение для субъектов и удостоверений, в которых `IsAuthenticated` является `false`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

`SignInAsync` принимает все субъекты и удостоверения, включая удостоверения, в которых `IsAuthenticated` является `false`.

#### <a name="new-behavior"></a>Новое поведение

По умолчанию `SignInAsync` создает исключение для субъектов и удостоверений, в которых `IsAuthenticated` является `false`. Есть новый флаг, который подавляет это поведение, но поведение по умолчанию изменилось.

#### <a name="reason-for-change"></a>Причина изменения

Старое поведение было проблематичным, так как по умолчанию эти участники отклонялись `[Authorize]` / `RequireAuthenticatedUser()`.

#### <a name="recommended-action"></a>Рекомендуемое действие

В ASP.NET Core 3.0 (предварительная версия 6) есть флаг `RequireAuthenticatedSignIn` в `AuthenticationOptions`, который является `true` по умолчанию. Установите для этого флага значение `false`, чтобы восстановить старое поведение.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
