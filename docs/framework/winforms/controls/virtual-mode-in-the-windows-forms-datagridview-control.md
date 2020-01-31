---
title: Виртуальный режим в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], virtual mode
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
ms.openlocfilehash: 0d82f0fc9946e5b61ea171f2f5d2ab5690db0c71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745443"
---
# <a name="virtual-mode-in-the-windows-forms-datagridview-control"></a>Виртуальный режим элемента управления DataGridView в Windows Forms
С помощью виртуального режима можно управлять взаимодействием между элементом управления <xref:System.Windows.Forms.DataGridView> и пользовательским кэшем данных. Чтобы реализовать виртуальный режим, задайте для свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и обработайте одно или несколько событий, описанных в этом разделе. Обычно обрабатывается по крайней мере событие `CellValueNeeded`, которое позволяет элементу управления выполнять поиск значений в кэше данных.  
  
## <a name="bound-mode-and-virtual-mode"></a>Связанный режим и виртуальный режим  
 Virtual mode is necessary only when you need to supplement or replace bound mode. In bound mode, you set the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property and the control automatically loads the data from the specified source and submits user changes back to it. You can control which of the bound columns are displayed, and the data source itself typically handles operations such as sorting.  
  
## <a name="supplementing-bound-mode"></a>Supplementing Bound Mode  
 You can supplement bound mode by displaying unbound columns along with the bound columns. This is sometimes called "mixed mode" and is useful for displaying things like calculated values or user-interface (UI) controls.  
  
 Because unbound columns are outside the data source, they are ignored by the data source's sorting operations. Therefore, when you enable sorting in mixed mode, you must manage the unbound data in a local cache and implement virtual mode to let the <xref:System.Windows.Forms.DataGridView> control interact with it.  
  
 For more information about using virtual mode to maintain the values in unbound columns, see the examples in the <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> property and <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> class reference topics.  
  
## <a name="replacing-bound-mode"></a>Replacing Bound Mode  
 If bound mode does not meet your performance needs, you can manage all your data in a custom cache through virtual-mode event handlers. For example, you can use virtual mode to implement a just-in-time data loading mechanism that retrieves only as much data from a networked database as is necessary for optimal performance. This scenario is particularly useful when working with large amounts of data over a slow network connection or with client machines that have a limited amount of RAM or storage space.  
  
 For more information about using virtual mode in a just-in-time scenario, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>Virtual-Mode Events  
 If your data is read-only, the `CellValueNeeded` event may be the only event you will need to handle. Additional virtual-mode events let you enable specific functionality like user edits, row addition and deletion, and row-level transactions.  
  
 Some standard <xref:System.Windows.Forms.DataGridView> events (such as events that occur when users add or delete rows, or when cell values are edited, parsed, validated, or formatted) are useful in virtual mode, as well. You can also handle events that let you maintain values not typically stored in a bound data source, such as cell ToolTip text, cell and row error text, cell and row shortcut menu data, and row height data.  
  
 For more information about implementing virtual mode to manage read/write data with a row-level commit scope, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
 For an example that implements virtual mode with a cell-level commit scope, see the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property reference topic.  
  
 The following events occur only when the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property is set to `true`.  
  
|Event|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Used by the control to retrieve a cell value from the data cache for display. This event occurs only for cells in unbound columns.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Used by the control to commit user input for a cell to the data cache. This event occurs only for cells in unbound columns.<br /><br /> Call the <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> method when changing a cached value outside of a <xref:System.Windows.Forms.DataGridView.CellValuePushed> event handler to ensure that the current value is displayed in the control and to apply any automatic sizing modes currently in effect.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Used by the control to indicate the need for a new row in the data cache.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Used by the control to determine whether a row has any uncommitted changes.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Used by the control to indicate that a row should revert to its cached values.|  
  
 The following events are useful in virtual mode, but can be used regardless of the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property setting.  
  
|события|Описание|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Используется элементом управления для указания на то, когда удаляются или добавляются строки, позволяя соответствующим образом обновить кэш данных.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Используется элементом управления для форматирования значений ячеек для вывода и анализа и проверки вводимых пользователем данных.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Используется элементом управления для получения текста всплывающей подсказки ячейки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> Подсказки ячеек отображаются только в том случае, если значение свойства <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> равно `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Используется элементом управления для извлечения текста ошибки ячейки или строки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> Вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> или метод <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> при изменении текста ошибки ячейки или строки, чтобы убедиться, что текущее значение отображается в элементе управления.<br /><br /> Глифы ошибок для ячеек и строк отображаются, когда `true`значения свойств <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> и <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A>.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Используется элементом управления для получения <xref:System.Windows.Forms.ContextMenuStrip> ячейки или строки, если свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> элемента управления задано или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Используется элементом управления для извлечения или сохранения сведений о высоте строки в кэше данных. Вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> при изменении сведений о высоте кэшированной строки за пределами <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> обработчика событий, чтобы гарантировать, что текущее значение используется в отображении элемента управления.|  
  
## <a name="best-practices-in-virtual-mode"></a>Рекомендации в виртуальном режиме  
 Если вы реализуете виртуальный режим для эффективной работы с большими объемами данных, необходимо также обеспечить эффективную работу с самим элементом управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения о эффективном использовании стилей ячеек, автоматического изменения размера, выбора и совместного использования строк см. [в разделе рекомендации по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
