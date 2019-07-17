---
ms.openlocfilehash: 01bbc49cb0febc5a29dafc7c311b848387a4094a
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803550"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>Добавление открытого свойства SelectionTextBrush при выделении текстового поля или поля пароля без графического элемента

|   |   |
|---|---|
|Подробные сведения|В приложениях WPF при [выделении текста без графических элементов](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) для <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> разработчики теперь могут задать новое свойство SelectionTextBrush, чтобы изменить отрисовку выбранного текста.  По умолчанию этот цвет меняется с <xref:System.Windows.SystemColors.HighlightTextBrushKey>.  Если выделение текста без использования графического элемента не включено, это свойство ничего не делает.|
|Предложение|Если выделение текста без графического элемента включено, вы можете использовать свойство <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> и <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> для изменения внешнего вида выбранного текста. Это можно сделать с помощью XAML:<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>|
|Область|Значительно|
|Версия|4.8|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType></li><li>[System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)</li><li>[System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)</li></ul>|

