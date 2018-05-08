---
title: Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: c777366124a3cc5f43df8efca54fc366245bcb75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a>Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms
`DataGridView` Элемент управления предоставляет множество параметров для настройки, как пользователи могут выбрать ячеек, строк и столбцов. Например можно включить выделение одного или нескольких элементов, выбор целых строк или столбцов, при щелчке ячейки или выбор целых строк или столбцов только в том случае, если пользователь щелкнет их заголовки, что позволяет также выделение ячеек. Если вы хотите предоставить собственный пользовательский интерфейс для выбора, можно отключить стандартные функции выбора и обрабатывать все команды выбора программным путем. Кроме того можно разрешить пользователям копировать выбранные значения в буфер обмена.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Режимы выделения содержимого элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 Описывает параметры для пользователей и программный выбор в элементе управления.  
  
 [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 Описывает, как настроить элемент управления для выбора одной строки, когда пользователь щелкает ячейку.  
  
 [Практическое руководство. Получение информации о выделенных пользователем ячейках, строках и столбцах элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 Описание работы с выбранными коллекциями ячеек, строк и столбцов.  
  
 [Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 Описывает способ включения поддержки буфера обмена в элементе управления.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойство.  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> свойство.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> класса.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> класса.  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> класса.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
