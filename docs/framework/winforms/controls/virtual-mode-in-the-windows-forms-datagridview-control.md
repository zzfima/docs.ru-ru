---
title: "Виртуальный режим элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView - элемент управления [Windows Forms], виртуальный режим"
ms.assetid: feae5d43-2848-4b1a-8ea7-77085dc415b5
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Виртуальный режим элемента управления DataGridView в Windows Forms
Виртуальный режим позволяет управлять взаимодействием между элементом управления <xref:System.Windows.Forms.DataGridView> и пользовательским кэшем данных.  Чтобы реализовать виртуальный режим, необходимо присвоить свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и обеспечить обработку одного или нескольких событий, описываемых в этом разделе.  Обычно используется, как минимум, обработчик событий `CellValueNeeded`, которое позволяет элементу управления производить поиск значений в кэше данных.  
  
## Связанный и виртуальный режимы  
 Виртуальный режим необходим, только когда требуется расширить или заменить связанный режим.  В связанном режиме задается свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A>, и элемент управления автоматически загружает данные из указанного источника и передает в него внесенные пользователем изменения.  При этом можно указывать, какие из связанных столбцов должны отображаться, а источник данных сам отвечает за выполнение таких операций, как сортировка.  
  
## Расширение связанного режима  
 Связанный режим можно расширить путем одновременного отображения связанных и несвязанных столбцов.  Иногда это называют "связанным режимом". Он может использоваться, например, для отображения вычисленных значений или элементов управления пользовательского интерфейса.  
  
 Поскольку несвязанные столбцы не относятся к источнику данных, они игнорируются при выполнении источником данных операций сортировки.  Поэтому при использовании сортировки в смешанном режиме необходимо обеспечить управление несвязанными данными в локальном кэше и реализовать виртуальный режим, чтобы элемент управления <xref:System.Windows.Forms.DataGridView> мог взаимодействовать с ним.  
  
 Для получения дополнительных сведений об использовании виртуального режима для сохранения значений в несвязанных столбцах см. примеры в справочных разделах, посвященных свойству <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=fullName> и классу <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>.  
  
## Замещение связанного режима  
 Если связанный режим не удовлетворяет требованиям производительности, можно обеспечить управление данными в пользовательском кэше посредством обработчиков событий виртуального режима.  Например, виртуальный режим может использоваться для реализации механизма JIT\-загрузки, с помощью которого из сетевой базы данных извлекается только такой объем данных, который не приведет к снижению производительности.  Этот сценарий особенно эффективен при работе с большими объемами данных через медленное сетевое подключение или при ограниченном объеме оперативной памяти или дискового пространства на клиентских компьютерах.  
  
 Дополнительные сведения об использовании виртуального режима в JIT\-сценариях см. в разделе [Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## События виртуального режима  
 Если данные доступны только для чтения, может понадобиться обработка только события `CellValueNeeded`.  Дополнительные события виртуального режима позволяют реализовать специальные возможности, такие как редактирование данных пользователем, добавление и удаление строк, а также транзакции на уровне строк.  
  
 Некоторые стандартные события элемента управления <xref:System.Windows.Forms.DataGridView> \(например, события, наступающие при добавлении или удалении строк пользователем, редактировании, преобразовании, проверке или форматировании значений ячеек\) также могут использоваться в виртуальном режиме.  Кроме того, существует возможность обработки событий, которые позволяют поддерживать значения, обычно не сохраняемые в связанном источнике данных. К таким значениям относятся: текст всплывающих подсказок для ячеек, текст ошибки для ячейки или строки, данные контекстного меню для ячейки или строки, а также данные о высоте строке.  
  
 Дополнительные сведения о реализации виртуального режима для управления данными, доступными для чтения и записи, с областью фиксации на уровне строк см. в разделе [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
 Пример реализации виртуального режима с областью фиксации на уровне ячеек см. в справочном разделе, посвященном свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
 Следующие события наступают, только если свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.  
  
|Событие|Описание|  
|-------------|--------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Используется элементом управления для извлечения значения ячейки из кэша данных для отображения.  Это событие происходит только для ячеек в несвязанных столбцах.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Используется элементом управления для сохранения введенного пользователем значения ячейки в кэш данных.  Это событие происходит только для ячеек в несвязанных столбцах.<br /><br /> При изменении значения, находящегося в кэше, вне обработчика событий <xref:System.Windows.Forms.DataGridView.CellValuePushed> следует вызвать метод <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A>, чтобы обеспечить отображение текущего значения в элементе управления и правильное применение текущего режима автоматического изменения размеров.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Используется элементом управления для указания на необходимость создания новой строки в кэше данных.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Используется элементом управления для определения наличия в строке несохраненных изменений.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Используется элементом управления для указания на то, что строке должны быть возвращены значения из кэша.|  
  
 Следующие события могут оказаться полезными в виртуальном режиме, однако могут использоваться вне зависимости от значения свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
|События|Описание|  
|-------------|--------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Используется элементом управления для указания на факт добавления или удаления строк, что позволяет соответствующим образом обновить кэш данных.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Используется элементом управления для форматирования отображаемых значений ячеек, а также анализа и проверки вводимых пользователем данных.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Используется элементом управления для извлечения текста всплывающей подсказки для ячейки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> Всплывающие подсказки для ячеек отображаются, только если свойство <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> имеет значение `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Используется элементом управления для извлечения текста ошибки для ячейки или строки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> При изменении текста ошибки для ячейки или строки следует вызвать метод <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> или <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A>, чтобы обеспечить отображение в элементе управления текущего значения.<br /><br /> Глифы ошибок для ячеек и строк отображаются, только если свойства <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> и <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A> имеют значение `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Используется элементом управления для извлечения ячейки или строки <xref:System.Windows.Forms.ContextMenuStrip>, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Используется элементом управления для извлечения или сохранения сведений о высоте строки в кэш данных.  При изменении сведений о высоте строки, находящихся в кэше, вне обработчика событий <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> следует вызвать метод <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A>, чтобы обеспечить использование текущего значения при отображении элемента управления.|  
  
## Рекомендации по использованию виртуального режима  
 При реализации виртуального режима в целях эффективной работы с большими объемами данных следует также обеспечить эффективность использования самого элемента управления <xref:System.Windows.Forms.DataGridView>.  Дополнительные сведения об эффективном использовании стилей ячеек, автоматического изменения размеров, выделения и совместного использования строк см. в разделе [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 [Оптимизация производительности элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)   
 [Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)