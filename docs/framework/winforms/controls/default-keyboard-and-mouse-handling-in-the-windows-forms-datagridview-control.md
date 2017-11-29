---
title: "Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d0f1ec3f1fe0b078da92c93cbb928075d7d462c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Выполняемая по умолчанию обработка событий мыши и клавиатуры элементом управления DataGridView в Windows Forms
В следующих таблицах описаны способы взаимодействия пользователей с <xref:System.Windows.Forms.DataGridView> управления посредством клавиатуры и мыши.  
  
> [!NOTE]
>  Чтобы настроить поведение клавиатуры, можно обрабатывать события на стандартной клавиатуре например <xref:System.Windows.Forms.Control.KeyDown>. В режиме редактирования, однако размещенного элемента управления редактирования получает ввод с клавиатуры и событиях клавиатуры не выполняется для <xref:System.Windows.Forms.DataGridView> элемента управления. Для обработки события редактирования элемента управления, присоединение обработчиков для редактирования элемента управления в <xref:System.Windows.Forms.DataGridView.EditingControlShowing> обработчика событий. Кроме того, можно настроить поведение клавиатуры в <xref:System.Windows.Forms.DataGridView> подкласс путем переопределения <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> и <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> методы.  
  
## <a name="default-keyboard-handling"></a>Стандартная обработка событий клавиатуры  
  
### <a name="basic-navigation-and-entry-keys"></a>Основные клавиши перехода и ввода  
  
|Клавиши или сочетания клавиш|Описание|  
|----------------------------|-----------------|  
|СТРЕЛКА ВНИЗ|Перемещение фокуса к ячейке, расположенной непосредственно под текущей ячейкой. Если фокус находится в последней строке, ничего не делает.|  
|СТРЕЛКА ВЛЕВО|Переход к предыдущей ячейке в строке. Если фокус находится в первой ячейке в строке, ничего не делает.|  
|СТРЕЛКА ВПРАВО|Перемещение фокуса к следующей ячейке в строке. Если фокус находится в последней ячейке в строке, ничего не делает.|  
|СТРЕЛКА ВВЕРХ|Перемещает фокус в ячейку непосредственно над текущей ячейки. Если фокус находится в первой строке, ничего не делает.|  
|ГЛАВНАЯ|Переход к первой ячейке в текущей строке.|  
|END|Передает фокус последней ячейке в текущей строке.|  
|PAGE DOWN|Прокручивает элемент управления вниз на количество строк, отображаемых полностью. Передает фокус последней полностью отображаемой строки без изменения столбцов.|  
|PAGE UP|Прокручивает элемент управления вверх на количество полностью отображаемых строк. Перемещение фокуса на первую строку отображается без изменения столбцов.|  
|TAB|Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `false`, фокус перемещается к следующей ячейке в текущей строке. Если фокус находится в последней ячейке строки, фокус перемещается к первой ячейке в следующей строке. Если фокус находится в последней ячейке в элементе управления, фокус перемещается к следующему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `true`, фокус перемещается к следующему элементу управления в последовательности табуляции родительского контейнера.|  
|SHIFT+TAB|Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `false`, фокус перемещается к предыдущей ячейке в текущей строке. Если фокус находится в первой ячейке строки, фокус перемещается в последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке в элементе управления, фокус перемещается к предыдущему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `true`, фокус перемещается к предыдущему элементу управления в последовательности табуляции родительского контейнера.|  
|CTRL + TAB|Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `false`, фокус перемещается к следующему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `true`, фокус перемещается к следующей ячейке в текущей строке. Если фокус находится в последней ячейке строки, фокус перемещается к первой ячейке в следующей строке. Если фокус находится в последней ячейке в элементе управления, фокус перемещается к следующему элементу управления в последовательности табуляции родительского контейнера.|  
|CTRL+SHIFT+TAB|Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `false`, фокус перемещается к предыдущему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если <xref:System.Windows.Forms.DataGridView.StandardTab%2A> значение свойства `true`, фокус перемещается к предыдущей ячейке в текущей строке. Если фокус находится в первой ячейке строки, фокус перемещается в последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке в элементе управления, фокус перемещается к предыдущему элементу управления в последовательности табуляции родительского контейнера.|  
|CTRL + СТРЕЛКА|Передает фокус самой крайней ячейке в направлении стрелки.|  
|CTRL + HOME|Переход к первой ячейке в элементе управления.|  
|CTRL + END|Перемещение фокуса в последнюю ячейку в элементе управления.|  
|CTRL + PAGE ВНИЗ ИЛИ ВВЕРХ|То же, как страница вниз или PAGE UP.|  
|F2|Переводит текущую ячейку в режим редактирования ячейки, если <xref:System.Windows.Forms.DataGridView.EditMode%2A> значение свойства <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> или <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|  
|F4|Если текущая ячейка находится <xref:System.Windows.Forms.DataGridViewComboBoxCell>, она переходит в режим редактирования и отображается список раскрывающегося списка.|  
|ALT + СТРЕЛКА ВВЕРХ ИЛИ ВНИЗ СТРЕЛКИ|Если текущая ячейка находится <xref:System.Windows.Forms.DataGridViewComboBoxCell>, она переходит в режим редактирования и отображается список раскрывающегося списка.|  
|ПРОБЕЛ|Если текущая ячейка находится <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, или <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, вызывает <xref:System.Windows.Forms.DataGridView.CellClick> и <xref:System.Windows.Forms.DataGridView.CellContentClick> события. Если текущая ячейка находится <xref:System.Windows.Forms.DataGridViewButtonCell>, также нажимает кнопку. Если текущая ячейка находится <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, также изменяет состояние флажка.|  
|ВВОД|Фиксирует все изменения в текущей ячейке и строку и фокус перемещается к ячейке, расположенной непосредственно под текущей ячейкой. Если фокус находится в последней строке, изменения сохраняются без перемещения фокуса.|  
|ESC|Если элемент управления находится в режиме редактирования, отменяет изменение. Если элемент управления не находится в режиме редактирования, отменяет изменения, внесенные в текущую строку, если элемент управления привязан к источнику данных с поддержкой редактирования или реализации виртуального режима с областью фиксации на уровне строк.|  
|СТИРАНИЕ НАЗАД|Удаление знака перед курсором, при редактировании ячейки.|  
|DELETE|Удаление знака после курсора, при редактировании ячейки.|  
|CTRL+ВВОД|Фиксирует все изменения в текущей ячейке без перемещения фокуса. Также фиксирует все изменения для текущей строки, если элемент управления привязан к источнику данных, которая поддерживает режим редактирования или виртуальной реализации с уровня строк области фиксации.|  
|CTRL+0|Вводит <xref:System.DBNull.Value?displayProperty=nameWithType> значение в текущей ячейке, если ячейки могут изменяться. По умолчанию, отображаемое значение для <xref:System.DBNull> значение ячейки является значение <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> свойство <xref:System.Windows.Forms.DataGridViewCellStyle> действует для текущей ячейки.|  
  
### <a name="selection-keys"></a>Выбор ключей  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> свойству `false` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойству <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, изменения в текущей ячейке с помощью клавиши навигации изменении выбора элементов в новую ячейку. SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, такое же поведение наблюдается, но со следующими дополнениями.  
  
|Клавиши или сочетания клавиш|Описание|  
|----------------------------|-----------------|  
|SHIFT + ПРОБЕЛ|Выбор всей строки или столбца (то же, как при щелчке заголовка строки или столбца).|  
|Клавиша навигации (клавиша со стрелкой, PAGE UP/DOWN, HOME, END)|Если выбран полной строки или столбца, изменение текущей ячейки в новой строки или столбца выделяет всей новой строки или столбца (в зависимости от режима выделения).|  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `false` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, изменение текущей ячейки в новую строку или столбец с помощью клавиатуры выделяет всей новой строки или столбца. SHIFT, CTRL и ALT не влияют на это поведение.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `true`, поведение не изменяется, но навигацию с помощью клавиатуры, удерживая нажатой клавишу SHIFT (включая сочетание клавиш CTRL + SHIFT) изменит выбора нескольких ячеек. Перед выполнением перехода элемент управления помечает текущую ячейку как базовую. При переходе, удерживая нажатой клавишу SHIFT, выделение включает все ячейки между базовой и текущей ячейки. Другие ячейки в элементе управления останется выбранным, если они были установлены, но они могут снимается, если с помощью клавиатуры временно помещает их между базовой и текущей ячейки.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `true` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, текущей ячейки и ячейки привязки происходит так же, но только полной строки или столбцы становится выбранным или невыбранным.  
  
## <a name="default-mouse-handling"></a>Стандартная обработка событий мыши  
  
### <a name="basic-mouse-handling"></a>Обработка основных событий мыши  
  
> [!NOTE]
>  Щелчок по ячейке левой кнопки мыши всегда изменяет текущую ячейку. Щелчок по ячейке правой кнопкой мыши открывается контекстное меню, если она доступна.  
  
|Действие мыши|Описание|  
|------------------|-----------------|  
|Левой кнопки мыши|Обеспечивает выбранная ячейка текущей ячейки, а также вызывает <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> событий.|  
|Левая кнопка мыши вверх|Вызывает событие <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Щелчок левой кнопкой мыши|Вызывает <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> события|  
|Левой кнопки мыши и перетащите на ячейки заголовка столбца|Если <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> свойство `true`, перемещает столбец, чтобы его можно перетащить в новое место.|  
  
### <a name="mouse-selection"></a>Выделение мышью  
 Поведение выделения не связан с средней кнопки мыши или колесиком мыши.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> свойству `false` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> свойству <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, происходит следующее.  
  
|Действие мыши|Описание|  
|------------------|-----------------|  
|Щелчок левой кнопкой мыши|Выделение только текущей ячейки, если пользователь щелкает ячейку. Нет выбора поведения при щелчке заголовка строки или столбца.|  
|Щелкните правой кнопкой мыши|Отображает контекстное меню, если он доступен.|  
  
 Такое же поведение наблюдается при <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, за исключением того, что в зависимости от режима выделения, щелкнув заголовок строки или столбца выбирает всей строки или столбца и установка значения текущей ячейки в первую ячейку в строке или столбце.  
  
 Если <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, щелкнув любую ячейку в строке или столбце выберет всей строки или столбца.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `true`, удерживая нажатой клавишу CTRL или SHIFT при щелчке ячейки изменит выбора нескольких ячеек.  
  
 Если щелкнуть ячейку удерживая нажатой клавишу CTRL, ячейки изменит свое состояние выбора всех остальных ячеек, сохраняя их текущее состояние выделения.  
  
 Если щелкнуть ячейки или ряда ячеек, удерживая нажатой клавишу SHIFT, выделение включает все ячейки между текущей ячейке и привязка ячейки, расположенной в позиции текущей ячейки до первого щелчка. Щелкните и перетащите курсор через несколько ячеек, ячейкой привязки при ячеек в начале операции перетаскивания. Последующие нажатия кнопки, нажатой клавишей SHIFT изменение текущей ячейки, но не базовой ячейки. Другие ячейки в элементе управления останется выбранным, если они были установлены, но они могут снимается, если навигации мыши временно помещает их между базовой и текущей ячейки.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `true` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, удерживая нажатой клавишу SHIFT при щелчке заголовка строки или столбца (в зависимости от режима выделения) будет изменить существующий выбор полных строк или столбцов, если такие Выбранный объект существует. В противном случае он снять выделение и начать новое выделение полных строк или столбцов. Удерживая нажатой клавишу CTRL при щелчке заголовка строки или столбца, однако будет добавлять или удалять выбранной строки или столбца из выделенной без изменения текущего выделения в противном случае.  
  
 Если <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> равно `true` и <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> равно <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> или <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, удерживая нажатой клавишу SHIFT или CTRL при щелчке ячейки ведет себя так же, за исключением того, что только полных строк и влияют на столбцы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
