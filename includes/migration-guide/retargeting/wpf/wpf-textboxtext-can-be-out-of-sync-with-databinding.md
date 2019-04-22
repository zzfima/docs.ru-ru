---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774420"
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
