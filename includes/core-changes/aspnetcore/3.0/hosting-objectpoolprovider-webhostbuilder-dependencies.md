---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901782"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Размещение. Удаление ObjectPoolProvider из зависимостей WebHostBuilder

В ходе оптимизации ASP.NET Core `ObjectPoolProvider` был удален из основного набора зависимостей. Отдельные компоненты, зависящие от `ObjectPoolProvider`, теперь добавляют его самостоятельно.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

`WebHostBuilder` предоставляет `ObjectPoolProvider` по умолчанию в контейнере DI.

#### <a name="new-behavior"></a>Новое поведение

`WebHostBuilder` не предоставляет `ObjectPoolProvider` по умолчанию в контейнере DI.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение было внесено для оптимизации ASP.NET Core.

#### <a name="recommended-action"></a>Рекомендованное действие

Если компонент требует `ObjectPoolProvider`, его необходимо добавить в зависимости с помощью `IServiceCollection`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
