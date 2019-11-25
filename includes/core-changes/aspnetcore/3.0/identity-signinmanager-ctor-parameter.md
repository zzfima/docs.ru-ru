---
ms.openlocfilehash: 56b394c4698f60baeb70d3c17d1abee5d867deb7
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394083"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Удостоверение: конструктор SignInManager принимает новый параметр

Начиная с ASP.NET Core 3.0 в конструктор `SignInManager` был добавлен новый параметр `IUserConfirmation<TUser>`. Подробную информацию см. на странице [aspnet/AspNetCore#8356](https://github.com/aspnet/AspNetCore/issues/8356).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Изменение позволит добавить поддержку новых потоков сообщений электронной почты и подтверждений в удостоверении.

#### <a name="recommended-action"></a>Рекомендуемое действие

При создании `SignInManager` вручную предоставьте реализацию `IUserConfirmation` или воспользуйтесь реализацией из внедрения зависимостей.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
