---
title: Сортировка данных в элементе управления DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742944"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Сортировка данных в элементе управления Windows Forms DataGridView

По умолчанию пользователи могут сортировать данные в элементе управления <xref:System.Windows.Forms.DataGridView>, щелкая заголовок столбца текстового поля (или нажав клавишу F3, когда в ячейке текстового поля нажимается .NET Framework 4.7.2 и более поздние версии). Можно изменить свойство <xref:System.Windows.Forms.DataGridViewColumn.SortMode> конкретных столбцов, чтобы разрешить пользователям сортировать по другим типам столбцов, если это имеет смысл. Можно также выполнять сортировку данных программным способом по любому столбцу или по нескольким столбцам.

## <a name="in-this-section"></a>В этом разделе

[Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
Описывает параметры сортировки данных в элементе управления.

[Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
Описывает, как разрешить пользователям сортировать по столбцам, которые не поддерживают сортировку по умолчанию.

[Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
Описывает, как программно сортировать данные и как настраивать сортировку с помощью <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType>ного события или путем реализации интерфейса <xref:System.Collections.IComparer>.

## <a name="reference"></a>Справочник

<xref:System.Windows.Forms.DataGridView>  
Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
Содержит справочную документацию по методу <xref:System.Windows.Forms.DataGridView.Sort%2A>.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
Содержит справочную документацию по перечислению <xref:System.Windows.Forms.DataGridViewColumnSortMode>.

## <a name="see-also"></a>См. также раздел

- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Типы столбцов элемента управления DataGridView в Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
