---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394367"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel. Адаптеры подключений удалены

В рамках переноса API pubternal в `public` концепция `IConnectionAdapter` была удалена из Kestrel. Адаптеры подключений заменяются соответствующим ПО промежуточного слоя, которое похоже на ПО промежуточного слоя HTTP в конвейере ASP.NET Core, но для подключений более низкого уровня. Журналы подключений и HTTPS перемещены из адаптеров соединений в соответствующее ПО промежуточного слоя. Эти методы расширения должны и дальше работать без проблем, но детали реализации изменились.

Подробную информацию см. на странице [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412). Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Компоненты расширяемости Kestrel были созданы с помощью `IConnectionAdapter`.

#### <a name="new-behavior"></a>Новое поведение

Компоненты расширяемости Kestrel созданы с помощью [ПО промежуточного слоя](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="reason-for-change"></a>Причина изменения

Это изменение предназначено для обеспечения более гибкой архитектуры расширяемости.

#### <a name="recommended-action"></a>Рекомендуемое действие

Преобразуйте все реализации `IConnectionAdapter`, чтобы [использовать новый шаблон ПО промежуточного слоя](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
