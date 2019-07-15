---
ms.openlocfilehash: 2674edc595d8e4e1e4c2ee42b39aa59265127462
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803185"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a>Периодически не удается выполнить прокрутку до нижнего элемента в ItemsControls (таких как ListBox и DataGrid) при использовании пользовательских DataTemplates

|   |   |
|---|---|
|Подробные сведения|В некоторых случаях ошибка в .NET Framework 4.5 приводит к тому, что ItemsControls (например, <xref:System.Windows.Controls.ListBox?displayProperty=name>, <xref:System.Windows.Controls.ComboBox?displayProperty=name>, <xref:System.Windows.Controls.DataGrid?displayProperty=name> и т. д.) не удается выполнить прокрутку до нижнего элемента при использовании пользовательских DataTemplates. Если попытка прокрутки предпринимается повторно (после прокрутки вверх), прокрутка будет работать.|
|Предложение|Эта проблема была устранена в .NET Framework 4.5.2 и может быть решена путем обновления до этой версии (или более поздней) платформы .NET Framework. Кроме того, пользователи по-прежнему могут перетаскивать полосы прокрутки к последним элементам в этих коллекциях, однако для успешного выполнения этой задачи это может потребоваться сделать дважды.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|

