---
ms.openlocfilehash: 63a38f33fef09577c5ed621727b8c38e4c7e1bdf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760939"
---
### <a name="the-default-hash-algorithm-for-wpfs-markup-compiler-is-now-sha256"></a>Алгоритмом хэширования для компилятора разметки WPF по умолчанию теперь является SHA256

|   |   |
|---|---|
|Подробные сведения|Компилятор разметки (MarkupCompiler) WPF предоставляет службы компиляции для файлов разметки XAML.  В .NET Framework 4.7.1 и более ранних версиях для вычисления значений контрольной суммы по умолчанию использовался хэш-алгоритм SHA1. С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.2, теперь по умолчанию используется алгоритм SHA256.  Это изменение затрагивает все поколения контрольной суммы для файлов разметки во время компиляции.|
|Предложение|Разработчикам приложений, предназначенных для .NET Framework 4.7.2 или более поздних версий, которым требуется вернуться к режиму хэширования SHA1, необходимо установить следующий флаг AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Разработчикам, которым требуется использовать хэширование SHA256 для версий целевой платформы ниже .NET Framework 4.7.2, необходимо задать следующий флаг AppContext.  Обратите внимание, что установленная версия .NET Framework должна быть 4.7.2 или выше.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Markup.DoNotUseSha256ForMarkupCompilerChecksumAlgorithm=false&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Прозрачный|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|

