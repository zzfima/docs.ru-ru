---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804924"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>Новые значения перечисления в перечислении PageRangeSelection WPF

|   |   |
|---|---|
|Подробные сведения|Было добавлено два новых члена (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> и <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) в перечисление <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.|
|Предложение|В большинстве случаев эти изменения не влияют на код пользователя. Однако следует изменить код, зависящий от конкретного числа элементов, существующих в вызовах <xref:System.Enum.GetNames(System.Type)> или <xref:System.Enum.GetValues(System.Type)> к типу <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
