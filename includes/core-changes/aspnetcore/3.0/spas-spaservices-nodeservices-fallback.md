---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522657"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a>Одностраничные приложения: SpaServices и NodeServices больше не переключаются на средство ведения журнала консоли

<xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> и <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> больше не отображают журналы консоли, если ведение журналов не настроено.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

`Microsoft.AspNetCore.SpaServices` и `Microsoft.AspNetCore.NodeServices` использовались для автоматического создания средства для ведения журналов консоли в тех случаях, если ведение журналов не было настроено.

#### <a name="new-behavior"></a>Новое поведение

`Microsoft.AspNetCore.SpaServices` и `Microsoft.AspNetCore.NodeServices` больше не отображают журналы консоли, если ведение журналов не настроено.

#### <a name="reason-for-change"></a>Причина изменения

Необходимость в согласованной реализации ведения журналов с другими пакетами ASP.NET Core.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вам нужно воспроизвести старое поведение, добавьте `services.AddLogging(builder => builder.AddConsole())` к своему методу `Setup.ConfigureServices`, чтобы настроить ведение журнала консоли.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

Отсутствуют

<!--

#### Affected APIs

Not detectable via API analysis

-->
