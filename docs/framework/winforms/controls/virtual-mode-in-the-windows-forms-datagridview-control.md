---
title: Виртуальный режим элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 2e5724da4442bbfcb0928c864f78744b946acc18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Виртуальный режим элемента управления DataGridView в Windows Forms
Виртуальный режим позволяет управлять взаимодействием между <xref:System.Windows.Forms.DataGridView> управления и пользовательские данные кэша. Чтобы реализовать виртуальный режим, задать <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойства `true` и обработать одно или несколько событий, описанные в этом разделе. Обычно используется, как минимум `CellValueNeeded` событие, которое позволяет производить поиск значений в кэше данных элемента управления.  
  
## <a name="bound-mode-and-virtual-mode"></a>Связанный и виртуальный режим  
 Виртуальный режим необходим только в том случае, если нужно будет дополнить или заменить связанный режим. В режиме привязки задать <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойства и элемента управления автоматически загружает данные из указанного источника и передает обратно в изменении пользователем. Можно управлять отображаемые привязанные столбцы, а сам источник данных, обычно обрабатывает операций, таких как сортировка.  
  
## <a name="supplementing-bound-mode"></a>Расширение связанного режима  
 Связанный режим можно расширить путем отображения несвязанных столбцов, а также связанных столбцов. Это иногда называется «смешанный режим» и может использоваться для отображения, например, вычисляемые значения или пользовательского интерфейса (UI) управляет.  
  
 Поскольку несвязанные столбцы не относятся к источнику данных, они учитываются операциями сортировки источника данных. Таким образом, при использовании сортировки в смешанном режиме, необходимо управлять несвязанными данными в локальном кэше и реализовать виртуальный режим, чтобы <xref:System.Windows.Forms.DataGridView> управления взаимодействовать с ним.  
  
 Дополнительные сведения об использовании виртуального режима для сохранения значений в несвязанных столбцов см. Примеры в <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> свойство и <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> класса справочные разделы.  
  
## <a name="replacing-bound-mode"></a>Замещение связанного режима  
 Если связанный режим не удовлетворяет вашим требованиям к производительности, можно управлять данными в пользовательском кэше посредством обработчиков событий в виртуальном режиме. Например, можно использовать виртуальный режим реализовать механизм, который извлекает только загрузка данных just-in-time столько из сетевой базы данных, которое необходимо для достижения оптимальной производительности. Этот сценарий особенно полезен при работе с большими объемами данных через медленное сетевое подключение или на клиентских компьютерах с ограниченным объемом оперативной памяти или дискового пространства.  
  
 Дополнительные сведения об использовании виртуального режима в сценарии на времени см. в разделе [реализация виртуального режима с JIT-загрузкой данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>События виртуальный режим  
 Если данные только для чтения, `CellValueNeeded` событие может быть только события, которые требуется обработать. Дополнительные события виртуального режима позволяют реализовать специальные возможности, такие как пользовательские изменения, добавления и удаления и транзакции на уровне строк.  
  
 Некоторые стандартные <xref:System.Windows.Forms.DataGridView> событий (например, события, которые возникают, когда пользователи добавления или удаления строк или значений ячеек редактировать, синтаксический анализ, проверки или в формате) могут использоваться в виртуальном режиме. Также можно обрабатывать события, которые позволяют поддерживать значения, обычно не сохраняемые в связанного источника данных, таких как текст всплывающей подсказки ячейки, ячейки и текст ошибки строки, ячейки и строки контекстное меню данные и данные высоту строк.  
  
 Дополнительные сведения о реализации виртуального режима для управления чтения и записи данных с областью фиксации на уровне строк см. в разделе [Пошаговое руководство: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Пример реализации виртуального режима с областью фиксации на уровне ячеек см. в разделе <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство справочном разделе.  
  
 Следующие события возникают только при <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойству `true`.  
  
|событие|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Используется для извлечения значения ячейки из кэша данных для отображения элемента управления. Это событие происходит только для ячеек в несвязанных столбцов.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Используется элементом управления для сохранения введенного пользователем для ячейки в кэш данных. Это событие происходит только для ячеек в несвязанных столбцов.<br /><br /> Вызовите <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> метод при изменении кэшированное значение за пределами <xref:System.Windows.Forms.DataGridView.CellValuePushed> обработчик событий можно убедиться, что текущее значение в элементе управления и применить любые режима автоматического изменения размеров в данный момент.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Чтобы указать необходимость новой строки в кэше данных, используемые элементом управления.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Чтобы определить, имеет ли строка незафиксированные изменения, используемые элементом управления.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Чтобы указать, что строке должны быть возвращены значения из кэша, используемые элементом управления.|  
  
 Следующие события полезны в виртуальном режиме, но может использоваться вне зависимости от <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение свойства.  
  
|События|Описание|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Чтобы указать, когда строки удаляются или добавлено, что соответствующим образом обновить кэш данных, используемые элементом управления.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Используется элементом управления для форматирования значений ячеек для отображения, а также для синтаксического анализа и проверки пользовательского ввода.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Используется для извлечения текста всплывающей подсказки ячейки элемента управления при <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойству или <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство `true`.<br /><br /> Всплывающие подсказки для ячеек отображаются только если <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> значение свойства `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Используется элементом управления для извлечения текста ошибки ячейку или строку при <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойству или <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство `true`.<br /><br /> Вызовите <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> метода или <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> метод, когда требуется текст ошибки ячейку или строку, чтобы убедиться, что текущее значение отображается в элементе управления.<br /><br /> Глиф ошибки ячеек и строк отображаются при <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> и <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> значений свойств, `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Используется элементом управления для получения ячейку или строку <xref:System.Windows.Forms.ContextMenuStrip> при управления <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойству или <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Для получения или сохранения сведений о высоте строк в кэше данных, используемые элементом управления. Вызовите <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> метод при изменении сведений о высоте строк кэшированных за пределами <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> обработчик событий, чтобы убедиться, что текущее значение используется при отображении элемента управления.|  
  
## <a name="best-practices-in-virtual-mode"></a>Рекомендации в виртуальном режиме  
 При реализации виртуального режима для эффективной работы с большими объемами данных, также следует убедиться, что вы работаете эффективно <xref:System.Windows.Forms.DataGridView> самого элемента управления. Дополнительные сведения об эффективном использовании стили ячеек, автоматического изменения размеров, выделения и совместного использования строк см. в разделе [масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
