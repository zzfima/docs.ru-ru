---
title: Обработка клавиатуры и мыши по умолчанию в элементе управления Windows Forms DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 97b8c8c3e418586bbc0053c358a2924484115a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969134"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Обработка клавиатуры и мыши по умолчанию в элементе управления Windows Forms DataGridView

В следующих таблицах описано, как пользователи могут взаимодействовать <xref:System.Windows.Forms.DataGridView> с элементом управления с помощью клавиатуры и мыши.  
  
> [!NOTE]
> Для настройки поведения клавиатуры можно выполнять стандартные события клавиатуры, такие как <xref:System.Windows.Forms.Control.KeyDown>. Однако в режиме редактирования размещаемый элемент управления редактирования получает ввод с клавиатуры, а для <xref:System.Windows.Forms.DataGridView> элемента управления не возникают события клавиатуры. Для обработки событий элемента управления редактирования присоедините обработчики к элементу управления редактированием в <xref:System.Windows.Forms.DataGridView.EditingControlShowing> обработчике событий. Кроме того, можно настроить поведение клавиатуры в <xref:System.Windows.Forms.DataGridView> подклассе путем <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> переопределения методов и <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> .  
  
## <a name="default-keyboard-handling"></a>Обработка клавиатуры по умолчанию  
  
### <a name="basic-navigation-and-entry-keys"></a>Основные клавиши навигации и ввода  
  
|Сочетание клавиш или ключа|Описание|  
|----------------------------|-----------------|  
|СТРЕЛКА ВНИЗ|Перемещает фокус на ячейку непосредственно под текущей ячейкой. Если фокус находится в последней строке, не выполняет никаких действий.|  
|СТРЕЛКА ВЛЕВО|Перемещает фокус на предыдущую ячейку в строке. Если фокус находится в первой ячейке строки, не выполняет никаких действий.|  
|СТРЕЛКА ВПРАВО|Перемещает фокус на следующую ячейку в строке. Если фокус находится в последней ячейке строки, не выполняет никаких действий.|  
|СТРЕЛКА ВВЕРХ|Перемещает фокус на ячейку непосредственно над текущей ячейкой. Если фокус находится в первой строке, не выполняет никаких действий.|  
|ГЛАВНАЯ|Перемещает фокус на первую ячейку в текущей строке.|  
|END|Перемещает фокус на последнюю ячейку в текущей строке.|  
|PAGE DOWN|Прокручивает элемент управления вниз на число полностью отображаемых строк. Перемещает фокус на последнюю полностью отображаемую строку без изменения столбцов.|  
|PAGE UP|Прокручивает элемент управления вверх на число полностью отображаемых строк. Перемещает фокус на первую отображаемую строку без изменения столбцов.|  
|TAB|Если значение `false`свойства равно, перемещает фокус на следующую ячейку в текущей строке. <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Если фокус уже находится в последней ячейке строки, перемещает фокус на первую ячейку в следующей строке. Если фокус находится в последней ячейке элемента управления, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение `true`свойства равно, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера. <xref:System.Windows.Forms.DataGridView.StandardTab%2A>|  
|SHIFT+TAB|Если значение `false`свойства равно, перемещает фокус на предыдущую ячейку в текущей строке. <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Если фокус уже находится в первой ячейке строки, перемещает фокус на последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке элемента управления, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение `true`свойства равно, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера. <xref:System.Windows.Forms.DataGridView.StandardTab%2A>|  
|CTRL + TAB|Если значение `false`свойства равно, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера. <xref:System.Windows.Forms.DataGridView.StandardTab%2A><br /><br /> Если значение `true`свойства равно, перемещает фокус на следующую ячейку в текущей строке. <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Если фокус уже находится в последней ячейке строки, перемещает фокус на первую ячейку в следующей строке. Если фокус находится в последней ячейке элемента управления, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.|  
|CTRL+SHIFT+TAB|Если значение `false`свойства равно, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера. <xref:System.Windows.Forms.DataGridView.StandardTab%2A><br /><br /> Если значение `true`свойства равно, перемещает фокус на предыдущую ячейку в текущей строке. <xref:System.Windows.Forms.DataGridView.StandardTab%2A> Если фокус уже находится в первой ячейке строки, перемещает фокус на последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке элемента управления, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.|  
|CTRL + СТРЕЛКА|Перемещает фокус на наиболее крайние ячейки в направлении стрелки.|  
|CTRL + HOME|Перемещает фокус на первую ячейку в элементе управления.|  
|CTRL + END|Перемещает фокус на последнюю ячейку в элементе управления.|  
|CTRL + PAGE ВНИЗ/ВВЕРХ|То же, что и страница, или страница выше.|  
|F2|Помещает текущую ячейку в режим редактирования ячейки, если <xref:System.Windows.Forms.DataGridView.EditMode%2A> свойство имеет <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> значение или <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Сортирует текущий столбец, если <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> свойство имеет <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>значение. Это то же самое, что и щелчок по заголовку текущего столбца. Доступно с момента .NET Framework 4.7.2. Чтобы включить эту функцию, приложения должны быть нацелены на .NET Framework 4.7.2 или более поздней версии или явно отказаться от улучшения специальных возможностей с помощью коммутаторов AppContext.|  
|F4|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewComboBoxCell>, переводит ячейку в режим редактирования и отображает раскрывающийся список.|  
|ALT + СТРЕЛКА "ВВЕРХ/ВНИЗ"|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewComboBoxCell>, переводит ячейку в режим редактирования и отображает раскрывающийся список.|  
|ПРОБЕЛ|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>или <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, вызывает <xref:System.Windows.Forms.DataGridView.CellClick> события и <xref:System.Windows.Forms.DataGridView.CellContentClick> . Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewButtonCell>, также нажимает кнопку. Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, также изменяет состояние проверки.|  
|ВВОД|Фиксирует все изменения в текущей ячейке и строке и перемещает фокус на ячейку непосредственно под текущей ячейкой. Если фокус находится в последней строке, все изменения фиксируются без перемещения фокуса.|  
|ESC|Если элемент управления находится в режиме редактирования, отменяет изменение. Если элемент управления не находится в режиме редактирования, возвращает все изменения, внесенные в текущую строку, если элемент управления привязан к источнику данных, поддерживающему редактирование или виртуальный режим, реализованного с областью фиксации на уровне строк.|  
|BACKSPACE|Удаляет символ перед точкой вставки при редактировании ячейки.|  
|DELETE|Удаляет символ после точки вставки при редактировании ячейки.|  
|CTRL+ВВОД|Фиксирует все изменения в текущей ячейке без перемещения фокуса. Также фиксирует все изменения в текущей строке, если элемент управления привязан к источнику данных, поддерживающему редактирование или виртуальный режим, реализованному с областью фиксации на уровне строк.|  
|CTRL+0|Если ячейка может быть изменена, вводит значениевтекущуюячейку.<xref:System.DBNull.Value?displayProperty=nameWithType> По умолчанию отображаемым значением для <xref:System.DBNull> значения ячейки является значение <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> свойства объекта, <xref:System.Windows.Forms.DataGridViewCellStyle> действующего для текущей ячейки.|  
  
### <a name="selection-keys"></a>Ключи выбора

 Если свойство имеет `false` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> для <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>свойства задано значение, то изменение текущей ячейки с помощью клавиш навигации позволяет изменить выделенный фрагмент на новую ячейку. <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> Клавиши SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если параметр <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>имеет значение или, то происходит такое же поведение, но со следующими дополнениями. <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
  
|Сочетание клавиш или ключа|Описание|  
|----------------------------|-----------------|  
|SHIFT + ПРОБЕЛ|Выбирает полную строку или столбец (то же, что и щелчок по заголовку строки или столбца).|  
|Клавиша навигации (клавиша со стрелкой, страница вверх/вниз, Главная, КОНЕЧная)|Если выбрана полная строка или столбец, то изменение текущей ячейки на новую строку или столбец приводит к перемещению выделения в новую строку или столбец (в зависимости от режима выбора).|  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> параметр имеет `false` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то изменение текущей ячейки на новую строку или столбец с помощью клавиатуры приводит к перемещению выделения в полную новую строку или столбец. Клавиши SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> параметр имеет `true`значение, поведение навигации не меняется, но при нажатии клавиш Shift (включая Ctrl + Shift) будет изменено выделение в нескольких ячейках. Перед началом навигации элемент управления помечает текущую ячейку как ячейку привязки. При нажатии клавиши SHIFT выделенные элементы будут содержать все ячейки между ячейками привязки и текущей ячейкой. Другие ячейки в элементе управления остаются выбранными, если они уже выбраны, но они могут быть невыбранными, если перемещение по клавиатуре временно помещает их между ячейкой привязки и текущей ячейкой.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> параметр имеет `true` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то поведение ячейки привязки и текущей ячейки будет одинаковым, но только полные строки или столбцы будут выбраны или не выбраны.  
  
## <a name="default-mouse-handling"></a>Обработка мыши по умолчанию
  
### <a name="basic-mouse-handling"></a>Базовая обработка мыши
  
> [!NOTE]
> Щелчок по ячейке с левой кнопкой мыши всегда изменяет текущую ячейку. Если щелкнуть ячейку с правой кнопкой мыши, откроется контекстное меню, когда оно будет доступно.  
  
|Действие мыши|Описание|  
|------------------|-----------------|  
|Нажатие левой кнопки мыши|Делает нажатой ячейку текущей ячейкой и вызывает <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> событие.|  
|Левая кнопка мыши вверх|Вызывает событие <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Щелчок левой кнопкой мыши|<xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> Вызывает события <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> и|  
|Нажатие левой кнопки мыши и перетаскивание ячейки заголовка столбца|Если свойство имеет `true`значение, перемещает столбец, чтобы его можно было удалить в новую точку. <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>|  
  
### <a name="mouse-selection"></a>Выбор мыши

 Нет выделения, связанного с средней кнопкой мыши или колесиком мыши.  
  
 Если свойство имеет `false` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> для свойства задано <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>значение, происходит следующее поведение. <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>  
  
|Действие мыши|Описание|  
|------------------|-----------------|  
|Нажмите левую кнопку мыши|Выбирает только текущую ячейку, если пользователь щелкает ячейку. Отсутствие выбора, если пользователь щелкает заголовок строки или столбца.|  
|Нажмите правую кнопку мыши|Отображает контекстное меню, если оно доступно.|  
  
 Такое же поведение возникает, когда <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> параметр имеет <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> значение или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, за исключением того, что в зависимости от режима выбора при щелчке заголовка строки или столбца выбирается полная строка или столбец и устанавливается текущая ячейка в первую ячейку строки или столбца.  
  
 Если <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> для <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> параметра задано <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>значение или, то при щелчке любой ячейки в строке или столбце будет выбрана полная строка или столбец.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> для`true`задано значение, то при нажатии клавиш CTRL или Shift будет изменено выделение в нескольких ячейках.  
  
 Если щелкнуть ячейку при нажатой клавише CTRL, ячейка изменит свое состояние выбора, тогда как все остальные ячейки сохраняют свое текущее состояние выбора.  
  
 Если щелкнуть ячейку или ряд ячеек, удерживая нажатой клавишу SHIFT, выделение включает все ячейки между текущей ячейкой и ячейкой привязки, расположенной в позиции текущей ячейки до первого щелчка. Если щелкнуть и перетащить указатель по нескольким ячейкам, то ячейка привязки является ячейкой, которую щелкнули в начале операции перетаскивания. Последующие нажатия клавиши SHIFT меняют текущую ячейку, но не ячейку привязки. Другие ячейки в элементе управления остаются выбранными, если они уже выбраны, но они могут стать невыбранными, если переход между ячейками привязки и текущей ячейкой временно помещается.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> параметр имеет `true` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, то при щелчке по заголовку строки или столбца (в зависимости от режима выбора) при нажатии клавиши Shift будет изменен существующий набор полных строк или столбцов, если такой элемент Выбор существует. В противном случае он очистит выбор и начнет новый выбор полных строк или столбцов. При щелчке заголовка строки или столбца при нажатии клавиши CTRL будет добавлен или удалена выбранная строка или столбец из текущего выделения без изменения текущего выделения.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> параметр имеет `true` значение и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> значение или<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то нажатие клавиши Shift или CTRL ведет себя так же, как только полные строки и столбцы.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
