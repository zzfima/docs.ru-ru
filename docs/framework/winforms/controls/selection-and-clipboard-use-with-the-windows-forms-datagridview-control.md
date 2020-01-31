---
title: Выбор и использование буфера обмена с элементом управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743064"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a>Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms
Элемент управления `DataGridView` предоставляет разнообразные параметры для настройки того, как пользователи могут выбирать ячейки, строки и столбцы. Например, можно включить единичное или множественное выделение, выбрать целые строки или столбцы, если пользователь щелкнул ячейки, или выбрать целые строки или столбцы только в том случае, если пользователи щелкают заголовки, что также позволяет выбрать ячейку. Если вы хотите предоставить собственный пользовательский интерфейс для выбора, можно отключить обычный выбор и все выбранные элементы программным способом. Кроме того, можно разрешить пользователям копировать выбранные значения в буфер обмена.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)  
 Описывает параметры для пользователя и программного выбора в элементе управления.  
  
 [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 Описывает, как настроить элемент управления для выбора одной строки, когда пользователь щелкнет ячейку.  
  
 [Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms](selected-cells-rows-and-columns-datagridview.md)  
 Описывает, как работать с выбранными коллекциями ячеек, строк и столбцов.  
  
 [Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 Описывает, как включить поддержку буфера обмена в элементе управления.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>.  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 Содержит справочную документацию по классу <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>.  
  
## <a name="see-also"></a>См. также:

- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
