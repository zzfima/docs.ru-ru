---
ms.openlocfilehash: a14395895c6be586c862d1b49aa6bf6669e4203a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68238009"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Вызов Items.Refresh для ListBox, ListView или DataGrid в WPF с выбранным элементом может привести к появлению в элементе повторяющихся записей

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, когда элементы выбраны в <xref:System.Windows.Controls.ListBox?displayProperty=name>, может привести к дублированию выбранных элементов в списке. Аналогичная проблема возникает с <xref:System.Windows.Controls.ListView?displayProperty=name> и <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Эта проблема устранена в EntityFramework 4.6.|
|Предложение|Эту проблему можно решить программным путем, отменив выбор элементов до вызова метода <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> и затем повторно выбрав их после завершения вызова. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
