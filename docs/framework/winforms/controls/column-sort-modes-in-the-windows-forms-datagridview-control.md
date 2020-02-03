---
title: Режимы сортировки столбцов в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744191"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> столбцы имеют три режима сортировки. Режим сортировки для каждого столбца задается с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> столбца, для которого можно задать одно из следующих <xref:System.Windows.Forms.DataGridViewColumnSortMode> значений перечисления.  
  
|Значение `DataGridViewColumnSortMode`|Description|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|По умолчанию для столбцов текстового поля. Если для выделения не используются заголовки столбцов, при щелчке заголовка столбца автоматически сортируются <xref:System.Windows.Forms.DataGridView> по этому столбцу и отображается глиф, указывающий порядок сортировки.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|По умолчанию для столбцов, не являющихся текстовыми полей. Этот столбец можно отсортировать программно; Однако он не предназначен для сортировки, поэтому для глифа сортировки не резервируется место.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Этот столбец можно отсортировать программно, и для глифа сортировки зарезервировано пространство.|  
  
 Может потребоваться изменить режим сортировки для столбца, который по умолчанию имеет значение <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>, если содержит значения, которые могут быть осмысленно упорядочены. Например, если имеется столбец базы данных, содержащий числа, представляющие состояния элементов, эти числа можно отобразить в виде соответствующих значков путем привязки столбца Image к столбцу базы данных. Затем числовые значения ячейки можно изменить на отображаемые значения изображения в обработчике события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. В этом случае установка свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> в значение <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> позволит пользователям сортировать столбец. Автоматическая сортировка позволяет пользователям группировать элементы, имеющие одинаковое состояние, даже если в состояниях, соответствующих числам, нет естественной последовательности. Столбцы флажков являются еще одним примером, где автоматическая сортировка полезна для группирования элементов в одном и том же состоянии.  
  
 Можно отсортировать <xref:System.Windows.Forms.DataGridView> программными средствами по значениям в любом столбце или в нескольких столбцах независимо от параметров <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>. Программная сортировка полезна, если необходимо предоставить собственный пользовательский интерфейс для сортировки или реализовать пользовательскую сортировку. Предоставление собственного пользовательского интерфейса сортировки полезно, например, при выборе режима выбора <xref:System.Windows.Forms.DataGridView> для включения выбора заголовка столбца. В этом случае, несмотря на то, что заголовки столбцов нельзя использовать для сортировки, все равно требуется, чтобы в заголовках отображался соответствующий глиф сортировки, поэтому следует задать для свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значение <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Столбцы, для которых задан режим программной сортировки, не отображают глиф сортировки автоматически. Для этих столбцов необходимо самостоятельно отобразить глиф, задав свойство <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>. Это необходимо, если требуется гибкость при пользовательской сортировке. Например, при сортировке <xref:System.Windows.Forms.DataGridView> по нескольким столбцам может потребоваться отобразить несколько глифов сортировки или без глифа сортировки.  
  
 Хотя можно программно отсортировать <xref:System.Windows.Forms.DataGridView> по любому столбцу, некоторые столбцы, например столбцы кнопок, могут не содержать значений, которые могут быть осмысленно упорядочены. Для этих столбцов параметр <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> указывает, что он никогда не будет использоваться для сортировки, поэтому нет необходимости зарезервировать место в заголовке для глифа сортировки.  
  
 При сортировке <xref:System.Windows.Forms.DataGridView> можно определить как столбец сортировки, так и порядок сортировки, проверив значения свойств <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A>. Эти значения не имеют смысла после пользовательской операции сортировки. Дополнительные сведения о пользовательской сортировке см. в разделе Настраиваемая сортировка далее в этом разделе.  
  
 При сортировке элемента управления <xref:System.Windows.Forms.DataGridView>, содержащего как связанные, так и несвязанные столбцы, значения в непривязанных столбцах не могут поддерживаться автоматически. Чтобы сохранить эти значения, необходимо реализовать виртуальный режим, задав свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значение `true` и обрабатывая события <xref:System.Windows.Forms.DataGridView.CellValueNeeded> и <xref:System.Windows.Forms.DataGridView.CellValuePushed>. Дополнительные сведения см. в разделе [инструкции. Реализация виртуального режима в элементе управления Windows Forms DataGridView](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). Сортировка по несвязанным столбцам в связанном режиме не поддерживается.  
  
## <a name="programmatic-sorting"></a>Программная сортировка  
 Можно отсортировать <xref:System.Windows.Forms.DataGridView> программным путем, вызвав метод <xref:System.Windows.Forms.DataGridView.Sort%2A>.  
  
 Перегрузка `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> принимает <xref:System.Windows.Forms.DataGridViewColumn> и значение перечисления <xref:System.ComponentModel.ListSortDirection> в качестве параметров. Эта перегрузка полезна при сортировке по столбцам со значениями, которые могут быть осмысленно упорядочены, но которые не нужно настраивать для автоматической сортировки. При вызове этой перегрузки и передаче столбца со значением <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>свойства <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> задаются автоматически, а соответствующий глиф сортировки отображается в заголовке столбца.  
  
> [!NOTE]
> Если элемент управления <xref:System.Windows.Forms.DataGridView> привязан к внешнему источнику данных путем установки свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A>, перегрузка метода `Sort(DataGridViewColumn,ListSortDirection)` не работает для непривязанных столбцов. Кроме того, если свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true`, эту перегрузку можно вызвать только для связанных столбцов. Чтобы определить, привязан ли столбец к данным, проверьте значение свойства <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>. Сортировка непривязанных столбцов в связанном режиме не поддерживается.  
  
## <a name="custom-sorting"></a>Пользовательская сортировка  
 <xref:System.Windows.Forms.DataGridView> можно настроить с помощью перегрузки `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> или путем обработки события <xref:System.Windows.Forms.DataGridView.SortCompare>.  
  
 Перегрузка метода `Sort(IComparer)` принимает экземпляр класса, который реализует интерфейс <xref:System.Collections.IComparer> в качестве параметра. Эта перегрузка полезна, если нужно предоставить настраиваемую сортировку. Например, если значения в столбце не имеют естественного порядка сортировки или если естественный порядок сортировки не подходит. В этом случае нельзя использовать автоматическую сортировку, но по-прежнему необходимо, чтобы пользователи могли сортировать, щелкая заголовки столбцов. Эту перегрузку можно вызвать в обработчике для события <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>, если заголовки столбцов не используются для выбора.  
  
> [!NOTE]
> Перегрузка метода `Sort(IComparer)` работает, только если элемент управления <xref:System.Windows.Forms.DataGridView> не привязан к внешнему источнику данных, а значение свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> — `false`. Чтобы настроить сортировку для столбцов, привязанных к внешнему источнику данных, необходимо использовать операции сортировки, предоставляемые источником данных. В виртуальном режиме необходимо предоставить собственные операции сортировки для несвязанных столбцов.  
  
 Чтобы использовать перегрузку метода `Sort(IComparer)`, необходимо создать собственный класс, реализующий интерфейс <xref:System.Collections.IComparer>. Этот интерфейс требует, чтобы класс реализовал метод <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>, в который <xref:System.Windows.Forms.DataGridView> передает <xref:System.Windows.Forms.DataGridViewRow>ные объекты в качестве входных данных при вызове перегрузки метода `Sort(IComparer)`. В этом случае можно вычислить правильный порядок строк на основе значений в любом столбце.  
  
 Перегрузка метода `Sort(IComparer)` не устанавливает свойства <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A>, поэтому для просмотра глифа сортировки необходимо всегда задавать свойство <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>.  
  
 В качестве альтернативы перегрузке метода `Sort(IComparer)` можно предоставить пользовательскую сортировку, реализовав обработчик для события <xref:System.Windows.Forms.DataGridView.SortCompare>. Это событие возникает, когда пользователи щелкают заголовки столбцов, настроенных для автоматической сортировки, или при вызове перегрузки `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>. Это событие возникает для каждой пары строк в элементе управления, что позволяет вычислить правильный порядок.  
  
> [!NOTE]
> Событие <xref:System.Windows.Forms.DataGridView.SortCompare> не возникает, если свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> задано или если значение свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> равно `true`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Сортировка данных в элементе управления DataGridView в Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
