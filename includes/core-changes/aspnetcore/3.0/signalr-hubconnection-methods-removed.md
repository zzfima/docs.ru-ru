---
ms.openlocfilehash: a56c5fc32b5fd274d5da0d9b295918f5ea3b345e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394471"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: методы HubConnection ResetSendPing и ResetTimeout были удалены

Методы `ResetSendPing` и `ResetTimeout` были удалены из API `HubConnection` в SignalR. Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2. Эти методы не будут доступны начиная с выпуска ASP.NET Core 3.0 (предварительная версия 4). Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#8543](https://github.com/aspnet/AspNetCore/issues/8543).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Интерфейсы API были доступны.

#### <a name="new-behavior"></a>Новое поведение

Интерфейсы API удалены.

#### <a name="reason-for-change"></a>Причина изменения

Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2.

#### <a name="recommended-action"></a>Рекомендуемое действие

Не используйте эти методы.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
