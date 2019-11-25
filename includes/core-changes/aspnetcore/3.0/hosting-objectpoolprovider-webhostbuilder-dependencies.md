---
ms.openlocfilehash: 16b9fde49f513643a37f65f3e926a34fc991c55a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393919"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a>Размещение. Удаление ObjectPoolProvider из зависимостей WebHostBuilder

В ходе оптимизации ASP.NET Core `ObjectPoolProvider` был удален из основного набора зависимостей. Отдельные компоненты, зависящие от `ObjectPoolProvider`, теперь добавляют его самостоятельно.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#5944](https://github.com/aspnet/AspNetCore/issues/5944).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

`WebHostBuilder` предоставляет `ObjectPoolProvider` по умолчанию в контейнере DI.

#### <a name="new-behavior"></a>Новое поведение

`WebHostBuilder` не предоставляет `ObjectPoolProvider` по умолчанию в контейнере DI.

#### <a name="reason-for-change"></a>Причина изменения

Это изменение было внесено для оптимизации ASP.NET Core.

#### <a name="recommended-action"></a>Рекомендуемое действие

Если компонент требует `ObjectPoolProvider`, его необходимо добавить в зависимости с помощью `IServiceCollection`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
