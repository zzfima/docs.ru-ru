---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901992"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a>Удостоверение. конструктор SignInManager принимает новый параметр

Начиная с ASP.NET Core 3.0 в конструктор `SignInManager` был добавлен новый параметр `IUserConfirmation<TUser>`. Подробную информацию см. на странице [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Изменение позволит добавить поддержку новых потоков сообщений электронной почты и подтверждений в удостоверении.

#### <a name="recommended-action"></a>Рекомендованное действие

При создании `SignInManager` вручную предоставьте реализацию `IUserConfirmation` или воспользуйтесь реализацией из внедрения зависимостей.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
