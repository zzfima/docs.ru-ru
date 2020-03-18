---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394183"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a>Kestrel. Удаление абстракций транспортировки и их преобразование в общедоступную версию

В рамках перехода от программного интерфейса типа "pubternal" API транспортного уровня Kestrel предоставляются в виде общедоступного интерфейса в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

- Абстракции, связанные с транспортировкой, были доступны в библиотеке `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions`.
- Свойство `ListenOptions.NoDelay` было доступно.

#### <a name="new-behavior"></a>Новое поведение

- Интерфейс `IConnectionListener` появился в библиотеке `Microsoft.AspNetCore.Connections.Abstractions`, предоставляя наиболее используемые функции из библиотеки `...Transport.Abstractions`.
- Теперь `NoDelay` можно использовать в параметрах транспорта (`LibuvTransportOptions` и `SocketTransportOptions`).
- `SchedulingMode` использовать нельзя.

#### <a name="reason-for-change"></a>Причина изменения

Выполнение переноса ASP.NET Core 3.0 с pubternal API.

#### <a name="recommended-action"></a>Рекомендованное действие

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!-- 

### Affected APIs

Not detectable via API analysis

-->
