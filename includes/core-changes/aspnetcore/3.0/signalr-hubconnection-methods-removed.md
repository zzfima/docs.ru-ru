---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901854"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a>SignalR: методы HubConnection ResetSendPing и ResetTimeout были удалены

Методы `ResetSendPing` и `ResetTimeout` были удалены из API `HubConnection` в SignalR. Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2. Эти методы не будут доступны начиная с выпуска ASP.NET Core 3.0 (предварительная версия 4). Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Интерфейсы API были доступны.

#### <a name="new-behavior"></a>Новое поведение

Интерфейсы API удалены.

#### <a name="reason-for-change"></a>Причина изменения

Эти методы изначально предназначались только для внутреннего использования, но стали общедоступными в ASP.NET Core 2.2.

#### <a name="recommended-action"></a>Рекомендованное действие

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
