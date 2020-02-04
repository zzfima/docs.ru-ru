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
 Виртуальный режим необходим только в том случае, если требуется дополнить или заменить связанный режим. В режиме с привязкой вы задаете свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A>, и элемент управления автоматически загружает данные из указанного источника и отправляет пользовательские изменения обратно в него. Можно управлять отображением связанных столбцов, а сам источник данных обычно обрабатывает такие операции, как сортировка.  
  
## <a name="supplementing-bound-mode"></a>Дополнительный связанный режим  
 Можно дополнить связанный режим, отображая несвязанные столбцы вместе с привязанными столбцами. Иногда это называется смешанным режимом и полезно для отображения таких элементов, как вычисляемые значения или элементы управления пользовательского интерфейса.  
  
 Поскольку несвязанные столбцы находятся за пределами источника данных, они игнорируются операциями сортировки источника данных. Таким образом, при включении сортировки в смешанном режиме необходимо управлять несвязанными данными в локальном кэше и реализовать виртуальный режим, чтобы позволить элементу управления <xref:System.Windows.Forms.DataGridView> взаимодействовать с ним.  
  
 Дополнительные сведения об использовании виртуального режима для сохранения значений в несвязанных столбцах см. в примерах, приведенных в разделе <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A?displayProperty=nameWithType> свойства и <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> справочные статьи по классам.  
  
## <a name="replacing-bound-mode"></a>Замена связанного режима  
 Если связанный режим не соответствует требованиям к производительности, вы можете управлять всеми данными в пользовательском кэше с помощью обработчиков событий виртуального режима. Например, можно использовать виртуальный режим для реализации механизма загрузки данных JIT, который извлекает только столько данных из сетевой базы данных, сколько необходимо для оптимальной производительности. Этот сценарий особенно полезен при работе с большими объемами данных через небольшое сетевое подключение или с клиентскими компьютерами с ограниченным объемом ОЗУ или дисковым пространством.  
  
 Дополнительные сведения об использовании виртуального режима в JIT-сценарии см. в разделе [Реализация виртуального режима с JIT-загрузкой данных в элементе управления Windows Forms DataGridView](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
## <a name="virtual-mode-events"></a>События виртуального режима  
 Если данные доступны только для чтения, то событием `CellValueNeeded` может быть единственное событие, которое нужно будет обрабатывать. Дополнительные события виртуального режима позволяют включить определенные функции, такие как изменение пользователей, Добавление и удаление строк, а также транзакции на уровне строк.  
  
 Некоторые стандартные <xref:System.Windows.Forms.DataGridView> события (такие как события, происходящие при добавлении или удалении пользователем строк или изменении значений ячеек, а также при редактировании, анализе, проверке или форматировании) полезны в виртуальном режиме. Кроме того, можно обрабатывать события, которые позволяют поддерживать значения, не хранящиеся в связанном источнике данных, например текст подсказки ячейки, текст ошибки ячейки и строки, данные контекстного меню ячеек и строк, а также данные высоты строк.  
  
 Дополнительные сведения о реализации виртуального режима для управления данными чтения и записи с областью фиксации на уровне строк см. в разделе [Пошаговое руководство. Реализация виртуального режима в элементе управления Windows Forms DataGridView](implementing-virtual-mode-wf-datagridview-control.md).  
  
 Пример, в котором реализуется виртуальный режим с областью фиксации на уровне ячейки, см. в разделе Справочник по свойствам <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
 Следующие события происходят, только если свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.  
  
|Событие|Description|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.CellValueNeeded>|Используется элементом управления для получения значения ячейки из кэша данных для вывода. Это событие возникает только для ячеек в непривязанных столбцах.|  
|<xref:System.Windows.Forms.DataGridView.CellValuePushed>|Используется элементом управления для фиксации введенных пользователем данных для ячейки в кэш данных. Это событие возникает только для ячеек в непривязанных столбцах.<br /><br /> Вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateCellValue%2A> при изменении кэшированного значения за пределами <xref:System.Windows.Forms.DataGridView.CellValuePushed> обработчика событий, чтобы убедиться в том, что текущее значение отображается в элементе управления и для применения режимов автоматического изменения размеров, действующих в данный момент.|  
|<xref:System.Windows.Forms.DataGridView.NewRowNeeded>|Используется элементом управления для указания необходимости в новой строке в кэше данных.|  
|<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>|Используется элементом управления для определения, содержит ли строка незафиксированные изменения.|  
|<xref:System.Windows.Forms.DataGridView.CancelRowEdit>|Используется элементом управления для указания на то, что строка должна вернуться к ее кэшированным значениям.|  
  
 Следующие события полезны в виртуальном режиме, но могут использоваться независимо от значения свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
|События|Description|  
|------------|-----------------|  
|<xref:System.Windows.Forms.DataGridView.UserDeletingRow><br /><br /> <xref:System.Windows.Forms.DataGridView.UserDeletedRow><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsRemoved><br /><br /> <xref:System.Windows.Forms.DataGridView.RowsAdded>|Используется элементом управления для указания на то, когда удаляются или добавляются строки, позволяя соответствующим образом обновить кэш данных.|  
|<xref:System.Windows.Forms.DataGridView.CellFormatting><br /><br /> <xref:System.Windows.Forms.DataGridView.CellParsing><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.CellValidated><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidating><br /><br /> <xref:System.Windows.Forms.DataGridView.RowValidated>|Используется элементом управления для форматирования значений ячеек для вывода и анализа и проверки вводимых пользователем данных.|  
|<xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded>|Используется элементом управления для получения текста всплывающей подсказки ячейки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> Подсказки ячеек отображаются только в том случае, если значение свойства <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> равно `true`.|  
|<xref:System.Windows.Forms.DataGridView.CellErrorTextNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowErrorTextNeeded>|Используется элементом управления для извлечения текста ошибки ячейки или строки, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.<br /><br /> Вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateCellErrorText%2A> или метод <xref:System.Windows.Forms.DataGridView.UpdateRowErrorText%2A> при изменении текста ошибки ячейки или строки, чтобы убедиться, что текущее значение отображается в элементе управления.<br /><br /> Глифы ошибок для ячеек и строк отображаются, когда `true`значения свойств <xref:System.Windows.Forms.DataGridView.ShowCellErrors%2A> и <xref:System.Windows.Forms.DataGridView.ShowRowErrors%2A>.|  
|<xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>|Используется элементом управления для получения <xref:System.Windows.Forms.ContextMenuStrip> ячейки или строки, если свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> элемента управления задано или свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true`.|  
|<xref:System.Windows.Forms.DataGridView.RowHeightInfoNeeded><br /><br /> <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed>|Используется элементом управления для извлечения или сохранения сведений о высоте строки в кэше данных. Вызовите метод <xref:System.Windows.Forms.DataGridView.UpdateRowHeightInfo%2A> при изменении сведений о высоте кэшированной строки за пределами <xref:System.Windows.Forms.DataGridView.RowHeightInfoPushed> обработчика событий, чтобы гарантировать, что текущее значение используется в отображении элемента управления.|  
  
## <a name="best-practices-in-virtual-mode"></a>Рекомендации в виртуальном режиме  
 Если вы реализуете виртуальный режим для эффективной работы с большими объемами данных, необходимо также обеспечить эффективную работу с самим элементом управления <xref:System.Windows.Forms.DataGridView>. Дополнительные сведения о эффективном использовании стилей ячеек, автоматического изменения размера, выбора и совместного использования строк см. [в разделе рекомендации по масштабированию элемента управления Windows Forms DataGridView](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- [Оптимизация производительности элемента управления DataGridView в Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
