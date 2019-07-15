---
ms.openlocfilehash: 22c67c687f5581c181acc4aeab8910c4467fd424
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858486"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>Вызов Items.Refresh для ListBox, ListView или DataGrid в WPF с выбранным элементом может привести к появлению в элементе повторяющихся записей

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 вызов ListBox.Items.Refresh из кода, когда элементы выбраны в <xref:System.Windows.Controls.ListBox?displayProperty=name>, может привести к дублированию выбранных элементов в списке. Аналогичная проблема возникает с <xref:System.Windows.Controls.ListView?displayProperty=name> и <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Эта проблема устранена в EntityFramework 4.6.|
|Предложение|Эту проблему можно решить программным путем, отменив выбор элементов до вызова метода <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> и затем повторно выбрав их после завершения вызова. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|

