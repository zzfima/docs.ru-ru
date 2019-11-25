---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394102"
---
### <a name="logging-debuglogger-class-made-internal"></a>Ведение журнала: класс DebugLogger стал внутренним

До версии ASP.NET Core 3.0 модификатор доступа `DebugLogger` имел атрибут `public`. В ASP.NET Core 3.0 модификатор доступа изменен на `internal`.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="reason-for-change"></a>Причина изменения

Изменение реализуется с такой целью:

* обеспечение согласованности с другими реализациями средства ведения журналов, например `ConsoleLogger`;
* уменьшение контактной зоны API.

#### <a name="recommended-action"></a>Рекомендуемое действие

Используйте метод расширения <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder`, чтобы включить ведение журналов отладки. <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> также имеет атрибут `public` на тот случай, если потребуется зарегистрировать службу вручную.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
