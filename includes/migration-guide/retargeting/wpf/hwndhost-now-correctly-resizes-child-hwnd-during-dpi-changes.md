---
ms.openlocfilehash: b92086c8ccf7592ce70b75bd31d4ea255c35b543
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803454"
---
### <a name="hwndhost-now-correctly-resizes-child-hwnd-during-dpi-changes"></a>HwndHost теперь правильно изменяет размеры дочерних HWND во время изменений DPI

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.7.2 и более ранних версий при запуске WPF в режиме поддержки на уровне монитора элементы управления, размещенные в <xref:System.Windows.Interop.HwndHost>, имели неправильный размер после изменения DPI, например при перемещении приложений с одного монитора на другой. Это исправление гарантирует, что размещенные элементы управления правильно изменяют размер.|
|Предложение|Чтобы приложение могло использовать эти изменения, необходимо запустить его на платформе .NET Framework 4.7.2 или более поздней версии и включить это поведение, установив следующий [параметр AppContext](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) в разделе <code>&lt;runtime&gt;</code> файла конфигурации приложения в значение <code>false</code>, как показано в следующем примере.<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Значительно|
|Version|4.8|
|Type|Изменение целевой платформы|
