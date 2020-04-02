---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345213"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a>SignalR. Протокол MessagePack для концентратора перемещен в пакет MessagePack 2.x

[Протокол концентратора MessagePack](/aspnet/core/signalr/messagepackhubprotocol) для ASP.NET Core SignalR использует [пакет NuGet MessagePack](https://www.nuget.org/packages/MessagePack) для сериализации MessagePack. ASP.NET Core 5.0 обновляет пакет с 1.x до последней версии пакета 2.x.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).

#### <a name="version-introduced"></a>Представленная версия

5.0 Предварительная версия 1

#### <a name="old-behavior"></a>Старое поведение

Чтобы сериализовать и десериализировать сообщения MessagePack, ASP.NET Core SignalR использовал пакет MessagePack 1.x.

#### <a name="new-behavior"></a>Новое поведение

ASP.NET Core SignalR использует для сериализации и десериализации сообщений MessagePack пакет MessagePack версии 2.x.

#### <a name="reason-for-change"></a>Причина изменения

Последние улучшения в пакете MessagePack версии 2.x принесли полезные функции.

#### <a name="recommended-action"></a>Рекомендованное действие

Это критическое изменение применяется в следующих случаях.

* При установке или настройке значений на <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.
* При использовании API MessagePack напрямую и протокола концентратора ASP.NET Core MessagePack SignalR в одном проекте. Вместо предыдущей версии будет загружена новая версия.

Руководство по миграции от авторов пакетов см. в статье [Переход с MessagePack версии 1.x на MessagePack версии 2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md). Затрагиваются некоторые аспекты сериализации и десериализации сообщений. В частности, имеются [изменения поведения, определяющие порядок сериализации значений DateTime](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
