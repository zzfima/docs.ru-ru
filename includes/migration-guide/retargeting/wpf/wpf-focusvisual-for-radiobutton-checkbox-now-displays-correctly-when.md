---
ms.openlocfilehash: 38c50244b1cee41bd95c232ac5d1691c59c55488
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760934"
---
### <a name="wpf-focusvisual-for-radiobutton-and-checkbox-now-displays-correctly-when-the-controls-have-no-content"></a>FocusVisual WPF для RadioButton и CheckBox теперь отображается корректно, если эти элементы управления не включают содержимое

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.1 и более ранних версий <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> и <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> WPF имеют несогласованные и (в классической теме и теме высокой контрастности) неправильные визуальные элементы фокуса.  Это происходит в случаях, когда для элементов управления не задано какое-либо содержимое.  Это может затруднять переход между темами и отображение визуального элемента фокуса. В .NET Framework 4.7.2 эти визуальные элементы стали более согласованными в разных темах и более видимыми в классической и контрастной темах.|
|Предложение|Разработчикам приложений, предназначенных для .NET Framework 4.7.2, которым требуется вернуться к поведению в .NET Framework 4.7.1, необходимо задать следующий флаг AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Разработчикам, желающим использовать это изменение при работе с целевой платформой версии ниже .NET Framework 4.7.2, необходимо установить следующие флаги AppContext. Обратите внимание, что все флаги должны быть заданы соответствующим образом, а установленная версия платформы .NET Framework должна быть не ниже 4.7.2. Для получения последних улучшений в приложениях WPF необходимо выбрать включение всех улучшений специальных возможностей более ранних версий. Для этого убедитесь, что оба переключателя AppContext, Switch.UseLegacyAccessibilityFeatures и Switch.UseLegacyAccessibilityFeatures.2, имеют значение false.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|

