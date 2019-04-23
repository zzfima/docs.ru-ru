---
ms.openlocfilehash: 0b42e320ba439a4cfc196471fc6dd4b3c15cd9d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804880"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Контрольные суммы рабочего процесса переведены с MD5 на SHA1

|   |   |
|---|---|
|Подробные сведения|Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для экземпляра рабочего процесса, используя алгоритм хэширования. В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.7 используется алгоритм SHA-1. Если в коде материализованы эти контрольные суммы, они будут несовместимы.|
|Предложение|Если код не может загрузить экземпляры рабочих процессов из-за ошибки контрольной суммы, попробуйте установить для параметра &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; переключателя <code>AppContext</code> значение true. В коде:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot;, true);&#13;&#10;</code></pre>Или в конфигурации:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseMD5ForWFDebugger=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7|
|Тип|Изменение целевой платформы|
