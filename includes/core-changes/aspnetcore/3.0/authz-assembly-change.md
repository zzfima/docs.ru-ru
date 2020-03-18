---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74101412"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>Авторизация. Перемещение перегрузки AddAuthorization в другую сборку

Основные методы `AddAuthorization`, используемые для размещения в `Microsoft.AspNetCore.Authorization`, были переименованы в `AddAuthorizationCore`. Старые методы `AddAuthorization` по-прежнему существуют, но теперь находятся в сборке `Microsoft.AspNetCore.Authorization.Policy`. Это не должно повлиять на приложения, использующие оба метода. Обратите внимание, что `Microsoft.AspNetCore.Authorization.Policy` теперь поставляется в общей платформе, а не в автономном пакете, как описано в разделе [Общая платформа. Из Microsoft.AspNetCore.App удалены сборки](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение
Методы `AddAuthorization` существовали в `Microsoft.AspNetCore.Authorization`.

#### <a name="new-behavior"></a>Новое поведение

Методы `AddAuthorization` существуют в `Microsoft.AspNetCore.Authorization.Policy`. `AddAuthorizationCore` — это новое имя старых методов.

#### <a name="reason-for-change"></a>Причина изменения

`AddAuthorization` — это лучшее имя метода для добавления всех общих служб, требуемых для авторизации.

#### <a name="recommended-action"></a>Рекомендованное действие

Добавьте ссылку на `Microsoft.AspNetCore.Authorization.Policy` или используйте вместо этого `AddAuthorizationCore`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
