---
ms.openlocfilehash: 1148d040aa3b292d5c37eb50224413b6ddd202e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804950"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase не распространяет исключения OnStart

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7 и более ранних версий исключения, возникшие при запуске службы, не распространяются на вызывающий объект <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>Начиная с приложений, предназначенных для .NET Framework 4.7.1, среда выполнения распространяет исключения в <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> для служб, которые не удается запустить.|
|Предложение|Если при запуске службы есть исключение, оно будет распространяться. Это поможет диагностировать случаи сбоя запуска служб. <br/>Если такое поведение нежелательно, от него можно отказаться, добавив следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Если приложение предназначено для версии до 4.7.1, но вы хотите использовать это поведение, добавьте следующий элемент &lt;AppContextSwitchOverrides&gt; в раздел &lt;runtime&gt; файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|
