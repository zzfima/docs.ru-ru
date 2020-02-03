---
title: Обработка клавиатуры и мыши по умолчанию в элементе управления DataGridView
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
ms.openlocfilehash: 36defff02450b40265c9b6801380cab78eabe5f3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746115"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Обработка клавиатуры и мыши по умолчанию в элементе управления Windows Forms DataGridView

В следующих таблицах описано, как пользователи могут взаимодействовать с элементом управления <xref:System.Windows.Forms.DataGridView> с помощью клавиатуры и мыши.  
  
> [!NOTE]
> Для настройки поведения клавиатуры можно выполнять стандартные события клавиатуры, такие как <xref:System.Windows.Forms.Control.KeyDown>. Однако в режиме редактирования размещаемый элемент управления редактирования получает ввод с клавиатуры и события клавиатуры не возникают для элемента управления <xref:System.Windows.Forms.DataGridView>. Для обработки событий элемента управления редактирования присоедините обработчики к элементу управления редактирования в обработчике событий <xref:System.Windows.Forms.DataGridView.EditingControlShowing>. Кроме того, можно настроить поведение клавиатуры в подклассе <xref:System.Windows.Forms.DataGridView>, переопределив методы <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> и <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A>.  
  
## <a name="default-keyboard-handling"></a>Обработка клавиатуры по умолчанию  
  
### <a name="basic-navigation-and-entry-keys"></a>Основные клавиши навигации и ввода  
  
|Сочетание клавиш или ключа|Description|  
|----------------------------|-----------------|  
|СТРЕЛКА ВНИЗ|Перемещает фокус на ячейку непосредственно под текущей ячейкой. Если фокус находится в последней строке, не выполняет никаких действий.|  
|СТРЕЛКА ВЛЕВО|Перемещает фокус на предыдущую ячейку в строке. Если фокус находится в первой ячейке строки, не выполняет никаких действий.|  
|СТРЕЛКА ВПРАВО|Перемещает фокус на следующую ячейку в строке. Если фокус находится в последней ячейке строки, не выполняет никаких действий.|  
|СТРЕЛКА ВВЕРХ|Перемещает фокус на ячейку непосредственно над текущей ячейкой. Если фокус находится в первой строке, не выполняет никаких действий.|  
|HOME|Перемещает фокус на первую ячейку в текущей строке.|  
|END|Перемещает фокус на последнюю ячейку в текущей строке.|  
|PAGE DOWN|Прокручивает элемент управления вниз на число полностью отображаемых строк. Перемещает фокус на последнюю полностью отображаемую строку без изменения столбцов.|  
|PAGE UP|Прокручивает элемент управления вверх на число полностью отображаемых строк. Перемещает фокус на первую отображаемую строку без изменения столбцов.|  
|TAB|Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `false`, перемещает фокус в следующую ячейку в текущей строке. Если фокус уже находится в последней ячейке строки, перемещает фокус на первую ячейку в следующей строке. Если фокус находится в последней ячейке элемента управления, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `true`, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.|  
|SHIFT + TAB|Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `false`, перемещает фокус на предыдущую ячейку в текущей строке. Если фокус уже находится в первой ячейке строки, перемещает фокус на последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке элемента управления, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `true`, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.|  
|CTRL + TAB|Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `false`, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `true`, перемещает фокус в следующую ячейку в текущей строке. Если фокус уже находится в последней ячейке строки, перемещает фокус на первую ячейку в следующей строке. Если фокус находится в последней ячейке элемента управления, перемещает фокус на следующий элемент управления в порядке табуляции родительского контейнера.|  
|CTRL + SHIFT + TAB|Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `false`, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.<br /><br /> Если значение свойства <xref:System.Windows.Forms.DataGridView.StandardTab%2A> равно `true`, перемещает фокус на предыдущую ячейку в текущей строке. Если фокус уже находится в первой ячейке строки, перемещает фокус на последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке элемента управления, перемещает фокус на предыдущий элемент управления в порядке табуляции родительского контейнера.|  
|CTRL + стрелка|Перемещает фокус на наиболее крайние ячейки в направлении стрелки.|  
|CTRL + HOME|Перемещает фокус на первую ячейку в элементе управления.|  
|CTRL + END|Перемещает фокус на последнюю ячейку в элементе управления.|  
|CTRL + PAGE ВНИЗ/ВВЕРХ|То же, что и страница, или страница выше.|  
|F2|Помещает текущую ячейку в режим редактирования ячейки, если значение свойства <xref:System.Windows.Forms.DataGridView.EditMode%2A> равно <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> или <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Сортирует текущий столбец, если значение свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. Это то же самое, что и щелчок по заголовку текущего столбца. Доступно с момента .NET Framework 4.7.2. Чтобы включить эту функцию, приложения должны быть нацелены на .NET Framework 4.7.2 или более поздней версии или явно отказаться от улучшения специальных возможностей с помощью коммутаторов AppContext.|  
|F4|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewComboBoxCell>, переводит ячейку в режим редактирования и отображает раскрывающийся список.|  
|ALT + СТРЕЛКА "ВВЕРХ/ВНИЗ"|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewComboBoxCell>, переводит ячейку в режим редактирования и отображает раскрывающийся список.|  
|SPACE|Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>или <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, вызывает события <xref:System.Windows.Forms.DataGridView.CellClick> и <xref:System.Windows.Forms.DataGridView.CellContentClick>. Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewButtonCell>, также нажимает кнопку. Если текущая ячейка является <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, также изменяет состояние проверки.|  
|ВВОД|Фиксирует все изменения в текущей ячейке и строке и перемещает фокус на ячейку непосредственно под текущей ячейкой. Если фокус находится в последней строке, все изменения фиксируются без перемещения фокуса.|  
|ESC|Если элемент управления находится в режиме редактирования, отменяет изменение. Если элемент управления не находится в режиме редактирования, возвращает все изменения, внесенные в текущую строку, если элемент управления привязан к источнику данных, поддерживающему редактирование или виртуальный режим, реализованного с областью фиксации на уровне строк.|  
|BACKSPACE|Удаляет символ перед точкой вставки при редактировании ячейки.|  
|DELETE|Удаляет символ после точки вставки при редактировании ячейки.|  
|CTRL + ВВОД|Фиксирует все изменения в текущей ячейке без перемещения фокуса. Также фиксирует все изменения в текущей строке, если элемент управления привязан к источнику данных, поддерживающему редактирование или виртуальный режим, реализованному с областью фиксации на уровне строк.|  
|CTRL + 0|Вводит <xref:System.DBNull.Value?displayProperty=nameWithType> значение в текущую ячейку, если ячейка может быть изменена. По умолчанию отображаемое значение для <xref:System.DBNull> значения ячейки — это значение свойства <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> <xref:System.Windows.Forms.DataGridViewCellStyle>, действующего для текущей ячейки.|  
  
### <a name="selection-keys"></a>Ключи выбора

 Если для свойства <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> задано значение `false` и для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> задано значение <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, то изменение текущей ячейки с помощью клавиш навигации позволяет изменить выделение на новую ячейку. Клавиши SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, то происходит такое же поведение, но со следующими дополнениями.  
  
|Сочетание клавиш или ключа|Description|  
|----------------------------|-----------------|  
|SHIFT + ПРОБЕЛ|Выбирает полную строку или столбец (то же, что и щелчок по заголовку строки или столбца).|  
|Клавиша навигации (клавиша со стрелкой, страница вверх/вниз, Главная, КОНЕЧная)|Если выбрана полная строка или столбец, то изменение текущей ячейки на новую строку или столбец приводит к перемещению выделения в новую строку или столбец (в зависимости от режима выбора).|  
  
 Если параметр <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `false` а <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то изменение текущей ячейки на новую строку или столбец с помощью клавиатуры приводит к перемещению выделенной строки в полную новую строку или столбец. Клавиши SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `true`, поведение навигации не изменяется, но переход с помощью клавиатуры при нажатии клавиши SHIFT (включая CTRL + SHIFT) приведет к изменению выбора из нескольких ячеек. Перед началом навигации элемент управления помечает текущую ячейку как ячейку привязки. При нажатии клавиши SHIFT выделенные элементы будут содержать все ячейки между ячейками привязки и текущей ячейкой. Другие ячейки в элементе управления остаются выбранными, если они уже выбраны, но они могут быть невыбранными, если перемещение по клавиатуре временно помещает их между ячейкой привязки и текущей ячейкой.  
  
 Если параметр <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `true` а <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, поведение ячейки привязки и текущей ячейки будет одинаковым, но только полные строки или столбцы будут выбраны или не выбраны.  
  
## <a name="default-mouse-handling"></a>Обработка мыши по умолчанию
  
### <a name="basic-mouse-handling"></a>Базовая обработка мыши
  
> [!NOTE]
> Щелчок по ячейке с левой кнопкой мыши всегда изменяет текущую ячейку. Если щелкнуть ячейку с правой кнопкой мыши, откроется контекстное меню, когда оно будет доступно.  
  
|Действие мыши|Description|  
|------------------|-----------------|  
|Нажатие левой кнопки мыши|Делает выбранную ячейку текущей ячейкой и вызывает событие <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType>.|  
|Левая кнопка мыши вверх|Вызывает событие <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Щелчок левой кнопкой мыши|Вызывает события <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType>|  
|Нажатие левой кнопки мыши и перетаскивание ячейки заголовка столбца|Если свойство <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> `true`, перемещает столбец, чтобы его можно было удалить в новую точку.|  
  
### <a name="mouse-selection"></a>Выбор мыши

 Нет выделения, связанного с средней кнопкой мыши или колесиком мыши.  
  
 Если свойство <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `false` и для свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> задано значение <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, происходит следующее поведение.  
  
|Действие мыши|Description|  
|------------------|-----------------|  
|Нажмите левую кнопку мыши|Выбирает только текущую ячейку, если пользователь щелкает ячейку. Отсутствие выбора, если пользователь щелкает заголовок строки или столбца.|  
|Нажмите правую кнопку мыши|Отображает контекстное меню, если оно доступно.|  
  
 Такое же поведение возникает, когда <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, за исключением того, что в зависимости от режима выбора, если щелкнуть заголовок строки или столбца, будет выбрана полная строка или столбец и установлена текущая ячейка в первой ячейке строки или столбца.  
  
 Если <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то при щелчке любой ячейки в строке или столбце выбирается полная строка или столбец.  
  
 Если для параметра <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> задано значение `true`, то при нажатии клавиш CTRL или SHIFT будет изменено выделение в нескольких ячейках.  
  
 Если щелкнуть ячейку при нажатой клавише CTRL, ячейка изменит свое состояние выбора, тогда как все остальные ячейки сохраняют свое текущее состояние выбора.  
  
 Если щелкнуть ячейку или ряд ячеек, удерживая нажатой клавишу SHIFT, выделение включает все ячейки между текущей ячейкой и ячейкой привязки, расположенной в позиции текущей ячейки до первого щелчка. Если щелкнуть и перетащить указатель по нескольким ячейкам, то ячейка привязки является ячейкой, которую щелкнули в начале операции перетаскивания. Последующие нажатия клавиши SHIFT меняют текущую ячейку, но не ячейку привязки. Другие ячейки в элементе управления остаются выбранными, если они уже выбраны, но они могут стать невыбранными, если переход между ячейками привязки и текущей ячейкой временно помещается.  
  
 Если параметр <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `true` а <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> имеет значение <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, то при щелчке заголовка строки или столбца (в зависимости от режима выбора) при нажатии клавиши SHIFT будет изменен существующий набор полных строк или столбцов, если такой выбор существует. В противном случае он очистит выбор и начнет новый выбор полных строк или столбцов. При щелчке заголовка строки или столбца при нажатии клавиши CTRL будет добавлен или удалена выбранная строка или столбец из текущего выделения без изменения текущего выделения.  
  
 Если для параметра <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> задано значение `true` а для параметра <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> задано значение <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, то нажатие клавиши SHIFT или CTRL ведет себя одинаково, за исключением того, что затрагиваются только полные строки и столбцы.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
