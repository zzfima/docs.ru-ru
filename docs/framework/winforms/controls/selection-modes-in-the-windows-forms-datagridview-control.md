---
title: Режимы выделения содержимого элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: dfe26e4749e6bff2d0ccdff47c6ea0b301880772
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960472"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Режимы выделения содержимого элемента управления DataGridView в Windows Forms
Иногда требуется, чтобы приложение выполняло действия на основе выбора пользователя в <xref:System.Windows.Forms.DataGridView> элементе управления. В зависимости от действий может потребоваться ограничить возможные виды выбора. Например, предположим, что приложение может напечатать отчет для выбранной в данный момент записи. В этом случае может потребоваться настроить <xref:System.Windows.Forms.DataGridView> элемент управления таким образом, чтобы при щелчке в любом месте строки всегда выбиралась вся строка и можно было выбрать только одну строку за раз.  
  
 Можно указать разрешенные параметры, задав <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> для свойства одно из следующих <xref:System.Windows.Forms.DataGridViewSelectionMode> значений перечисления.  
  
|Значение Датагридвиевселектионмоде|Описание|  
|-------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|При щелчке ячейки она выделяется. Заголовки строк и столбцов нельзя использовать для выбора.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|При щелчке ячейки она выделяется. При щелчке заголовка столбца выделяется весь столбец. Заголовки столбцов нельзя использовать для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|При щелчке ячейки или заголовка столбца выделяется весь столбец. Заголовки столбцов нельзя использовать для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|При щелчке ячейки или заголовка строки выделяется вся строка.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Режим выбора по умолчанию. При щелчке ячейки она выделяется. При щелчке заголовка строки выделяется вся строка.|  
  
> [!NOTE]
> Изменение режима выбора во время выполнения автоматически снимает текущее выделение.  
  
 По умолчанию пользователи могут выбирать несколько строк, столбцов или ячеек путем перетаскивания мышью, нажатием клавиш CTRL или SHIFT при выборе для расширения или изменения выделенного фрагмента или щелчка ячейки верхнего левого заголовка для выбора всех ячеек в элементе управления. Чтобы предотвратить такое поведение, присвойте <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> `false`свойству значение.  
  
 Режимы <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> и<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> позволяют пользователям удалять строки, выбирая их и нажимая клавишу DELETE. Пользователи могут удалять строки только в том случае, если текущая ячейка не находится в <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> режиме редактирования, свойство `true`имеет значение, а базовый источник данных поддерживает удаленное пользователем удаление строк. Обратите внимание, что эти параметры не предотвращают удаление программных строк.  
  
## <a name="programmatic-selection"></a>Программный выбор  
 Текущий режим выделения ограничит поведение программного выделения, а также выбор пользователя. Текущий выбор можно изменить программным путем, задав `Selected` свойство любых ячеек, строк или столбцов, имеющихся <xref:System.Windows.Forms.DataGridView> в элементе управления. Можно также выбрать все ячейки в элементе управления с помощью <xref:System.Windows.Forms.DataGridView.SelectAll%2A> метода, в зависимости от режима выбора. Чтобы очистить выбор, используйте <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> метод.  
  
 Если свойство имеет `true`значение, можно добавить <xref:System.Windows.Forms.DataGridView> или `Selected` удалить элементы из выбора, изменив свойство элемента. <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> В противном случае `Selected` при установке `true` свойства в значение для одного элемента автоматически удаляются другие элементы из выбора.  
  
 Обратите внимание, что изменение значения <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> свойства не приводит к изменению текущего выделения.  
  
 Коллекцию выбранных в данный момент ячеек, строк или столбцов можно получить <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>с помощью свойств <xref:System.Windows.Forms.DataGridView> , <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> элемента управления. Доступ к этим свойствам неэффективен, если выбрана каждая ячейка в элементе управления. Чтобы избежать снижения производительности в этом случае, сначала используйте <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> метод. Кроме того, доступ к этим коллекциям для определения количества выбранных ячеек, строк или столбцов может быть неэффективным. Вместо <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>этого следует использовать метод, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>или <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> , передав <xref:System.Windows.Forms.DataGridViewElementStates.Selected> значение.  
  
> [!TIP]
>  Пример кода, демонстрирующий программное использование выбранных ячеек, можно найти в <xref:System.Windows.Forms.DataGridView> обзоре класса.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка режима выбора элемента управления Windows Forms DataGridView](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
