---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858623"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>Доступ к выделенным элементам DataGrid WPF из события UnloadingRow DataGrid может привести к исключению NullReferenceException

|   |   |
|---|---|
|Подробнее|Из-за ошибки в .NET Framework 4.5 обработчики событий <xref:System.Windows.Controls.DataGrid>, которые выполняют удаление строки, могут привести к созданию исключения <xref:System.NullReferenceException?displayProperty=name> при попытке получить доступ к свойствам <xref:System.Windows.Controls.DataGrid> или <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>.|
|Предложение|Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
