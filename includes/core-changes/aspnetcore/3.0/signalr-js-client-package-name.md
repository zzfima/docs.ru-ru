---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394444"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR. Имя пакета клиента JavaScript изменено

В ASP.NET Core 3.0 (предварительная версия 7) имя клиентского пакета JavaScript для SignalR изменилось с `@aspnet/signalr` на `@microsoft/signalr`. Изменение имени отражает тот факт, что SignalR используется не только в приложениях ASP.NET Core благодаря поддержке Службы Azure SignalR.

Чтобы отреагировать на это изменение, измените ссылки в файлах *package.JSON*, а также инструкциях `require` и `import` ECMAScript. Это переименование не повлияет на API.

Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет клиента назывался `@aspnet/signalr`.

#### <a name="new-behavior"></a>Новое поведение

Пакет клиента называется `@microsoft/signalr`.

#### <a name="reason-for-change"></a>Причина изменения

Изменение имени отражает тот факт, что SignalR используется не только в приложениях ASP.NET Core благодаря поддержке Службы Azure SignalR.

#### <a name="recommended-action"></a>Рекомендуемое действие

Переключитесь на новый пакет `@microsoft/signalr`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Нет

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
