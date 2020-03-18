---
ms.openlocfilehash: f814703e187726d3988787fac52e5049988fd4d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803456"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Контрольные суммы рабочего процесса XAML для символов изменены с SHA1 на SHA256

|   |   |
|---|---|
|Подробнее|Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для файла XAML рабочего процесса, используя алгоритм хэширования. В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS. Начиная с .NET Framework 4.7 алгоритм по умолчанию изменен на SHA-1. Начиная с .NET Framework 4.8 алгоритм по умолчанию изменен на SHA256.|
|Предложение|Если код не может загрузить экземпляры рабочих процессов или найти подходящие символы из-за ошибки контрольной суммы, попробуйте установить для параметра <code>AppContext</code>&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; значение true. В коде:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre>Или в конфигурации:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.8|
|Type|Изменение целевой платформы|
