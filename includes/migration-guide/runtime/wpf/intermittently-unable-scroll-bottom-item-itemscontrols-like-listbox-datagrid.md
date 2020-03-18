---
ms.openlocfilehash: 9c2ee4ba66deb7c3b33698963add2b8a7e70069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803185"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Периодически не удается выполнить прокрутку до нижнего элемента в ItemsControls (таких как ListBox и DataGrid) при использовании пользовательских DataTemplates

|   |   |
|---|---|
|Подробнее|В некоторых случаях ошибка в .NET Framework 4.5 приводит к тому, что ItemsControls (например, <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name> и т. д.) не удается выполнить прокрутку до нижнего элемента при использовании пользовательских DataTemplates. Если попытка прокрутки предпринимается повторно (после прокрутки вверх), прокрутка будет работать.|
|Предложение|Эта проблема была устранена в .NET Framework 4.5.2 и может быть решена путем обновления до этой версии (или более поздней) платформы .NET Framework. Кроме того, пользователи по-прежнему могут перетаскивать полосы прокрутки к последним элементам в этих коллекциях, однако для успешного выполнения этой задачи это может потребоваться сделать дважды.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
