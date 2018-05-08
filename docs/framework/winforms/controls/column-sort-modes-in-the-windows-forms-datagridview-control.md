---
title: Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: 9ebcfc435fcc7d2b0dfbfe3004d958c73dd1347c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> столбцы имеют три режима сортировки. Режим сортировки для каждого столбца указывается с помощью <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойство столбца, который может быть присвоено одно из следующих <xref:System.Windows.Forms.DataGridViewColumnSortMode> значений перечисления.  
  
|Значение `DataGridViewColumnSortMode`|Описание|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|По умолчанию для столбцов текстовых полей. Если заголовки столбцов не используются для выбора, щелкнув заголовок столбца автоматически сортирует <xref:System.Windows.Forms.DataGridView> по этому столбцу и выводу глифа с указанием порядка сортировки.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|По умолчанию для столбцов, не являющихся — текстовое поле. Этот столбец можно сортировать программным образом. Однако он не предназначен для сортировки, поэтому место не резервируется для глифа сортировки.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Этот столбец можно сортировать программным образом и резервируется место для глифа сортировки.|  
  
 Может потребоваться изменить режим сортировки для столбца значение по умолчанию <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> , если он содержит значения, которые могут быть осмысленно упорядочены. Например если столбец базы данных, содержащий числа, представляющие состояния элементов, можно отобразить эти числа как соответствующие значки путем привязки к столбцу базы данных столбец типа image. Затем можно преобразовать числовые значения ячеек в графические значения в обработчике <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> событий. В этом случае установка <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> позволит пользователям отсортировать столбец. Автоматическая сортировка позволяет пользователям группировать элементы, имеющие такое же состояние, даже если соответствующие номера состояниям имеют естественную последовательности. Столбцы флажков представляют собой еще один пример, когда автоматическая сортировка полезно для группирования элементов в том же состоянии.  
  
 Можно сортировать <xref:System.Windows.Forms.DataGridView> программными средствами по значениям в одном столбце или в нескольких столбцах, независимо от того, <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> параметры. Программная сортировка может быть полезно, если вы хотите предоставить собственный пользовательский интерфейс (UI) для сортировки или при реализации пользовательской сортировки. Предоставление собственного пользовательского интерфейса сортировки будет полезно, например, при задании <xref:System.Windows.Forms.DataGridView> режим выделения, чтобы включить выбор заголовка столбца. Таким образом, несмотря на то, что заголовки столбцов не может использоваться для сортировки, необходимо все заголовки для отображения соответствующий глиф сортировки, поэтому необходимо установить <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Установка режима программная сортировка столбцов, не отображают глиф сортировки автоматически. Для этих столбцов должен отображаться глиф самостоятельно, задав <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> свойство. Это необходимо, чтобы обеспечить гибкость в пользовательской сортировки. Например, при сортировке <xref:System.Windows.Forms.DataGridView> по нескольким столбцам, может потребоваться отобразить нескольких или ни одного глифа сортировки.  
  
 Несмотря на то, что программная сортировка <xref:System.Windows.Forms.DataGridView> по любому столбцу, некоторые столбцы, например столбцы кнопок, может не содержать значений, которые могут быть осмысленно упорядочены. Для этих столбцов <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> указывает, что он не будут использоваться для сортировки, поэтому нет необходимости резервирует место в заголовке для глифа сортировки.  
  
 Когда <xref:System.Windows.Forms.DataGridView> — сортировать, можно определить столбец сортировки и порядок сортировки по значениям свойств <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> свойства. Эти значения не имеют смысла после проведения пользовательской сортировки. Дополнительные сведения о пользовательской сортировке см. раздел пользовательская сортировка далее в этом разделе.  
  
 Когда <xref:System.Windows.Forms.DataGridView> сортируется элемент управления, содержащий связанные и несвязанные столбцы, автоматическое сохранение значений в несвязанных столбцов невозможно. Для сохранения этих значений, необходимо реализовать виртуальный режим, задав <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойства `true` и обработка <xref:System.Windows.Forms.DataGridView.CellValueNeeded> и <xref:System.Windows.Forms.DataGridView.CellValuePushed> события. Дополнительные сведения см. в разделе [как: реализация виртуального режима в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). Сортировка по несвязанным столбцам в связанном режиме не поддерживается.  
  
## <a name="programmatic-sorting"></a>Программная сортировка  
 Можно сортировать <xref:System.Windows.Forms.DataGridView> программным образом путем вызова его <xref:System.Windows.Forms.DataGridView.Sort%2A> метод.  
  
 `Sort(DataGridViewColumn,ListSortDirection)` Перегруженная версия <xref:System.Windows.Forms.DataGridView.Sort%2A> принимает <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.ComponentModel.ListSortDirection> значение перечисления в качестве параметров. Эта перегрузка может использоваться при сортировке столбцов со значениями, которые могут быть осмысленно упорядочены, однако, вы не хотите настроить для автоматической сортировки. При вызове этой перегрузки и передаче столбца с <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значение свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> свойства устанавливаются автоматически и соответствующий глиф сортировки отображается в заголовке столбца.  
  
> [!NOTE]
>  Когда <xref:System.Windows.Forms.DataGridView> элемент управления привязан к внешнему источнику данных, задав <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойства `Sort(DataGridViewColumn,ListSortDirection)` перегруженный метод не работает для несвязанных столбцов. Кроме того, когда <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство `true`, эту перегрузку можно вызвать только для связанных столбцов. Чтобы определить, является ли столбец с привязкой к данным, проверьте <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> значение свойства. Сортировка несвязанных столбцов в связанном режиме не поддерживается.  
  
## <a name="custom-sorting"></a>Пользовательская сортировка  
 Вы можете настроить <xref:System.Windows.Forms.DataGridView> с помощью `Sort(IComparer)` перегруженная версия <xref:System.Windows.Forms.DataGridView.Sort%2A> метод либо посредством обработки <xref:System.Windows.Forms.DataGridView.SortCompare> событий.  
  
 `Sort(IComparer)` Перегруженный метод принимает экземпляр класса, который реализует <xref:System.Collections.IComparer> интерфейс в качестве параметра. Эта перегрузка может использоваться, если вы хотите пользовательской сортировки; Например, если значения в столбце не имеют естественного порядка сортировки или когда естественный порядок сортировки не подходит. В этом случае нельзя использовать автоматическую сортировку, но вы по-прежнему можете пользователям сортировать, щелкая заголовки столбцов. Эту перегрузку можно вызвать в обработчике <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> событие, если заголовки столбцов не используются для выбора.  
  
> [!NOTE]
>  `Sort(IComparer)` Перегруженный метод работает, только если <xref:System.Windows.Forms.DataGridView> элемент управления не привязан к внешнему источнику данных и <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение свойства `false`. Для настройки сортировки для столбцов, привязанных к внешнему источнику данных, необходимо использовать операции сортировки, предоставляемые в источнике данных. В виртуальном режиме необходимо предоставить свои собственные операции сортировки для несвязанных столбцов.  
  
 Для использования `Sort(IComparer)` перегрузка метода, необходимо создать собственный класс, реализующий <xref:System.Collections.IComparer> интерфейса. Этому интерфейсу требуется класс для реализации <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> метод, к которому <xref:System.Windows.Forms.DataGridView> передает <xref:System.Windows.Forms.DataGridViewRow> объектов в качестве входных при `Sort(IComparer)` вызове перегруженного метода. Таким образом можно вычислить правильный порядок строк на основе значений в любом столбце.  
  
 `Sort(IComparer)` Перегруженный метод не устанавливает <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> properties, поэтому необходимо задать <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> свойство для отображения глифа сортировки.  
  
 В качестве альтернативы для `Sort(IComparer)` перегрузка метода, вы можете предоставить пользовательская сортировка по реализации обработчика для <xref:System.Windows.Forms.DataGridView.SortCompare> события. Это событие возникает, когда пользователь щелкает заголовки столбцов, настроенным для автоматической сортировки или при вызове `Sort(DataGridViewColumn,ListSortDirection)` перегрузки <xref:System.Windows.Forms.DataGridView.Sort%2A> метод. Это событие возникает для каждой пары строк в элементе управления, позволяя определить их правильный порядок.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.SortCompare> Событие не происходит, когда <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойству или при <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение свойства `true`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>  
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
