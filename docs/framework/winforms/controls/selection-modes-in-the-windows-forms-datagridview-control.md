---
title: Режимы выделения содержимого элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: 43f3648a9c7d64fb4fb900c7df3f01bc18d729b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Режимы выделения содержимого элемента управления DataGridView в Windows Forms
Иногда требуется, чтобы приложение для выполнения действий, основываясь на выборе пользователя в пределах <xref:System.Windows.Forms.DataGridView> элемента управления. В зависимости от действий может потребоваться ограничить типы выбора, в которых возможны. Например предположим, что приложение можно распечатать отчет для выбранных записей. В этом случае может потребоваться настроить <xref:System.Windows.Forms.DataGridView> элемента управления, щелкнув в любом месте внутри строки выделяет всю строку, и таким образом можно выбрать только одну строку за раз.  
  
 Можно указать, задав допускается выбор <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> в одно из следующих <xref:System.Windows.Forms.DataGridViewSelectionMode> значений перечисления.  
  
|Значение DataGridViewSelectionMode|Описание|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|При щелчке ячейки выделяется. Заголовки строк и столбцов не может использоваться для выбора.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|При щелчке ячейки выделяется. Щелкнув заголовок столбца выбирает весь столбец. Заголовки столбцов не может использоваться для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|Выделение всего столбца по щелчку ячейки или заголовок столбца. Заголовки столбцов не может использоваться для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|Щелкнув ячейку или строку заголовка выделяет всю строку.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Режим выбора по умолчанию. При щелчке ячейки выделяется. При щелчке заголовка строки выделяет всю строку.|  
  
> [!NOTE]
>  Изменение режима выделения во время выполнения автоматически отменяет текущее выделение.  
  
 По умолчанию пользователи могут выбрать несколько строк, столбцов или ячеек с помощью перетаскивания мышью при нажатой клавишу CTRL или SHIFT во время расширения или изменения области выделения, или щелкнув ячейку левого верхнего заголовка, чтобы выделить все ячейки в элементе управления. Чтобы предотвратить такое поведение, присвойте <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> свойства `false`.  
  
 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> И <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> режимы позволяют удалять строки, выбрав их и нажав клавишу DELETE. Пользователи могут удалить строки только в том случае, если текущая ячейка не находится в режиме редактирования <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> свойству `true`, и в источнике данных поддерживает удаление строк пользователем. Обратите внимание, что эти параметры не препятствуют удалению строк программным.  
  
## <a name="programmatic-selection"></a>Программный выбор  
 Текущий режим выделения ограничивает возможности программного выделения, а также выбора пользователя. Текущее выделение можно изменить программно, установив `Selected` свойства любого ячеек, строк или столбцов в <xref:System.Windows.Forms.DataGridView> элемента управления. Можно также выделить все ячейки в элементе управления через <xref:System.Windows.Forms.DataGridView.SelectAll%2A> метод в зависимости от режима выделения. Чтобы снять выделение, используйте <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> метод.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> свойству `true`, можно добавить <xref:System.Windows.Forms.DataGridView> элементов, или удалите их из списка выбранных, изменив `Selected` свойство элемента. В противном случае установка `Selected` свойства `true` для одного элемента автоматически удаляет другие элементы из выделения.  
  
 Обратите внимание, что изменение значения <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойства не изменяет текущее выделение.  
  
 Можно получить коллекцию выделенных ячеек, строк или столбцов с помощью <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> свойства <xref:System.Windows.Forms.DataGridView> элемента управления. Доступ к этим свойствам неэффективно при каждой ячейки в элементе управления. Чтобы избежать снижения производительности в этом случае, используйте <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> метод первой. Кроме того доступ к этим коллекциям для определения числа выделенных ячеек, строк или столбцов может быть неэффективным. Вместо этого следует использовать <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>, или <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> метод, передавая <xref:System.Windows.Forms.DataGridViewElementStates.Selected> значение.  
  
> [!TIP]
>  Пример кода, демонстрирующий программное использование выделенных ячеек можно найти в <xref:System.Windows.Forms.DataGridView> Общие сведения о классе.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridViewSelectionMode>  
 [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
