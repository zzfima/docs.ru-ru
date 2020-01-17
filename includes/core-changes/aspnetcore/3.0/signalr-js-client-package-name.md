---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901896"
---
### <a name="signalr-javascript-client-package-name-changed"></a>SignalR. Имя пакета клиента JavaScript изменено

В ASP.NET Core 3.0 (предварительная версия 7) имя клиентского пакета JavaScript для SignalR изменилось с `@aspnet/signalr` на `@microsoft/signalr`. Изменение имени отражает тот факт, что SignalR используется не только в приложениях ASP.NET Core благодаря поддержке Службы Azure SignalR.

Чтобы отреагировать на это изменение, измените ссылки в файлах *package.JSON*, а также инструкциях `require` и `import` ECMAScript. Это переименование не повлияет на API.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Пакет клиента назывался `@aspnet/signalr`.

#### <a name="new-behavior"></a>Новое поведение

Пакет клиента называется `@microsoft/signalr`.

#### <a name="reason-for-change"></a>Причина изменения

Изменение имени отражает тот факт, что SignalR используется не только в приложениях ASP.NET Core благодаря поддержке Службы Azure SignalR.

#### <a name="recommended-action"></a>Рекомендованное действие

Переключитесь на новый пакет `@microsoft/signalr`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
