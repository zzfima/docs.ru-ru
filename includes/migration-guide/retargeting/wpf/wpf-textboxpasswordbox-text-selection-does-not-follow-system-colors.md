---
ms.openlocfilehash: 3f88c8b80518aa65c082dc3da2d75b5221dd00f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234032"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a>Выделенный текст в текстовом поле или поле пароля WPF не соответствуют системным цветам

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.7.1 и более ранних версий <code>System.Windows.Controls.TextBox</code> и <code>System.Windows.Controls.PasswordBox</code> WPF могли отображать выделенный текст только в слое декоративных элементов. В некоторых системных темах это приводило к скрытию текста, что делало его трудно читаемым.  В .NET Framework 4.7.2 и более поздних версий разработчики имеют возможность включить механизм отрисовки выбранных участков не на основе декоративных элементов, что устраняет эту проблему.|
|Предложение|Разработчикам, желающим использовать это изменение, необходимо задать следующий флаг AppContext соответствующим образом.  Чтобы использовать эту функцию, должна быть установлена версия .NET Framework 4.7.2 или более поздняя. Для включения выбора не на основе декоративных элементов используйте следующий флаг AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
