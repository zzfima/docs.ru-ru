---
ms.openlocfilehash: 81b104d8e5a9ccc8e790c3b16e4837cfa0c0def5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859045"
---
### <a name="serialport-background-thread-exceptions"></a>Исключения фонового потока SerialPort

|   |   |
|---|---|
|Подробнее|Фоновые потоки, созданные с помощью потоков <xref:System.IO.Ports.SerialPort>, больше не завершают процесс при возникновении исключений ОС. <br/>В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, процесс завершался при возникновении исключений операционной системы в фоновом потоке, созданном с помощью потока <xref:System.IO.Ports.SerialPort>. <br/>В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, фоновые потоки ожидают события ОС, связанные с активным последовательным портом, и могут аварийно завершиться в некоторых случаях, например при внезапном удалении последовательного порта.|
|Предложение|Для приложений, предназначенных для .NET Framework 4.7.1, можно отказаться от обработки исключений, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в .NET Framework 4.7.1 или более поздней версии, можно включить обработку исключений, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|
