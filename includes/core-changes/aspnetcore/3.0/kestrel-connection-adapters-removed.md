---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901891"
---
### <a name="kestrel-connection-adapters-removed"></a>Kestrel. Адаптеры подключений удалены

В рамках переноса API pubternal в `public` концепция `IConnectionAdapter` была удалена из Kestrel. Адаптеры подключений заменяются соответствующим ПО промежуточного слоя, которое похоже на ПО промежуточного слоя HTTP в конвейере ASP.NET Core, но для подключений более низкого уровня. Журналы подключений и HTTPS перемещены из адаптеров соединений в соответствующее ПО промежуточного слоя. Эти методы расширения должны и дальше работать без проблем, но детали реализации изменились.

Подробную информацию см. на странице [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412). Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Компоненты расширяемости Kestrel были созданы с помощью `IConnectionAdapter`.

#### <a name="new-behavior"></a>Новое поведение

Компоненты расширяемости Kestrel созданы с помощью [ПО промежуточного слоя](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="reason-for-change"></a>Причина изменения

Это изменение предназначено для обеспечения более гибкой архитектуры расширяемости.

#### <a name="recommended-action"></a>Рекомендованное действие

Преобразуйте все реализации `IConnectionAdapter`, чтобы [использовать новый шаблон ПО промежуточного слоя](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
