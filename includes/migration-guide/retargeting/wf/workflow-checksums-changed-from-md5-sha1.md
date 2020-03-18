---
ms.openlocfilehash: 0b42e320ba439a4cfc196471fc6dd4b3c15cd9d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859163"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Контрольные суммы рабочего процесса переведены с MD5 на SHA1

|   |   |
|---|---|
|Подробнее|Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для экземпляра рабочего процесса, используя алгоритм хэширования. В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.7 используется алгоритм SHA-1. Если в коде материализованы эти контрольные суммы, они будут несовместимы.|
|Предложение|Если код не может загрузить экземпляры рабочих процессов из-за ошибки контрольной суммы, попробуйте установить для параметра <code>AppContext</code>Switch.System.Activities.UseMD5ForWFDebugger&quot; переключателя &quot; значение true. В коде:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot;, true);&#13;&#10;</code></pre>Или в конфигурации:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseMD5ForWFDebugger=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7|
|Type|Изменение целевой платформы|
