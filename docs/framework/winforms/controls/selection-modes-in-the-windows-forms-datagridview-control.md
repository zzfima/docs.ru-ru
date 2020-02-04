---
title: Режимы выбора в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743036"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Режимы выделения содержимого элемента управления DataGridView в Windows Forms

Иногда требуется, чтобы приложение выполняло действия на основе выбора пользователя в элементе управления <xref:System.Windows.Forms.DataGridView>. В зависимости от действий может потребоваться ограничить возможные виды выбора. Например, предположим, что приложение может напечатать отчет для выбранной в данный момент записи. В этом случае может потребоваться настроить элемент управления <xref:System.Windows.Forms.DataGridView> таким образом, чтобы при щелчке в любом месте строки всегда выбиралась вся строка, и можно было выбрать только одну строку за раз.

Можно указать допустимые значения, задав для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> одно из следующих <xref:System.Windows.Forms.DataGridViewSelectionMode> значений перечисления.

|Значение Датагридвиевселектионмоде|Description|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|При щелчке ячейки она выделяется. Заголовки строк и столбцов нельзя использовать для выбора.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|При щелчке ячейки она выделяется. При щелчке заголовка столбца выделяется весь столбец. Заголовки столбцов нельзя использовать для сортировки.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|При щелчке ячейки или заголовка столбца выделяется весь столбец. Заголовки столбцов нельзя использовать для сортировки.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|При щелчке ячейки или заголовка строки выделяется вся строка.|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|Режим выбора по умолчанию. При щелчке ячейки она выделяется. При щелчке заголовка строки выделяется вся строка.|

> [!NOTE]
> Изменение режима выбора во время выполнения автоматически снимает текущее выделение.

По умолчанию пользователи могут выбирать несколько строк, столбцов или ячеек путем перетаскивания мышью, нажатием клавиш CTRL или SHIFT при выборе для расширения или изменения выделенного фрагмента или щелчка ячейки верхнего левого заголовка для выбора всех ячеек в элементе управления. Чтобы предотвратить такое поведение, задайте для свойства <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> значение `false`.

Режимы <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> и <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> позволяют пользователям удалять строки, выбирая их и нажимая клавишу DELETE. Пользователи могут удалять строки только в том случае, если текущая ячейка не находится в режиме редактирования, свойство <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> имеет значение `true`, а базовый источник данных поддерживает удаленное пользователем удаление строк. Обратите внимание, что эти параметры не предотвращают удаление программных строк.

## <a name="programmatic-selection"></a>Программный выбор

Текущий режим выделения ограничит поведение программного выделения, а также выбор пользователя. Текущий выбор можно изменить программным путем, установив свойство `Selected` любых ячеек, строк или столбцов, имеющихся в элементе управления <xref:System.Windows.Forms.DataGridView>. Можно также выбрать все ячейки в элементе управления с помощью метода <xref:System.Windows.Forms.DataGridView.SelectAll%2A>, в зависимости от режима выбора. Чтобы очистить выбор, используйте метод <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>.

Если свойство <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `true`, можно добавить элементы <xref:System.Windows.Forms.DataGridView> или удалить их из выделения, изменив свойство `Selected` элемента. В противном случае при установке свойства `Selected` в значение `true` для одного элемента автоматически удаляются другие элементы из выбора.

Обратите внимание, что изменение значения свойства <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> не приводит к изменению текущего выделения.

Коллекцию выбранных в данный момент ячеек, строк или столбцов можно получить с помощью свойств <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> элемента управления <xref:System.Windows.Forms.DataGridView>. Доступ к этим свойствам неэффективен, если выбрана каждая ячейка в элементе управления. Чтобы избежать снижения производительности в этом случае, сначала используйте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Кроме того, доступ к этим коллекциям для определения количества выбранных ячеек, строк или столбцов может быть неэффективным. Вместо этого следует использовать метод <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A>или <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>, передав значение <xref:System.Windows.Forms.DataGridViewElementStates.Selected>.

> [!TIP]
> Пример кода, демонстрирующий программное использование выбранных ячеек, можно найти в обзоре класса <xref:System.Windows.Forms.DataGridView>.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
