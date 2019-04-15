---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234781"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF TextBox.Text может быть не синхронизирован с привязкой данных

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях свойство <xref:System.Windows.Controls.TextBox.Text> отражает предыдущее значение привязанного к данным свойства, если свойство изменяется во время операции записи с привязкой к данным.|
|Предложение|Это не должно иметь отрицательных последствий. Однако можно восстановить прежнее поведение, установив свойству <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> значение <code>false</code>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
