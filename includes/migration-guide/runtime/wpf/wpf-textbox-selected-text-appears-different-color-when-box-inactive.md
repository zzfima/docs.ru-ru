---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235958"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>Выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будет отображаться цветом, отличным от того, когда элемент управления является активным.|
|Предложение|Чтобы восстановить прежнее поведение (.NET Framework 4.0), задайте для свойства <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> значение <code>false</code>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
