---
ms.openlocfilehash: de73145273ad5aa5c19de55525417cfc3305b86d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804899"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Вызов Items.Refresh для ListBox, ListView или DataGrid в WPF с выбранным элементом может привести к появлению в элементе повторяющихся записей

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, когда элементы выбраны в <xref:System.Windows.Controls.ListBox?displayProperty=name>, может привести к дублированию выбранных элементов в списке. Аналогичная проблема возникает с <xref:System.Windows.Controls.ListView?displayProperty=name> и <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Эта проблема устранена в EntityFramework 4.6.|
|Предложение|Эту проблему можно решить с помощью программных средств, отменив выбор элементов до вызова метода <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> и затем повторно выбрав их после завершения вызова. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
