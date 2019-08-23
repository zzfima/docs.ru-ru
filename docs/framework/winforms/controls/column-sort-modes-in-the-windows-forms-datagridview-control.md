---
title: Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d0d743ccae38d101eda5bb9780b33ae18dfb608a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918453"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView>столбцы имеют три режима сортировки. Режим сортировки для каждого столбца задается с помощью <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойства столбца, для которого можно задать одно из следующих <xref:System.Windows.Forms.DataGridViewColumnSortMode> значений перечисления.  
  
|Значение`DataGridViewColumnSortMode`|Описание|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|По умолчанию для столбцов текстового поля. Если для выделения не используются заголовки столбцов, <xref:System.Windows.Forms.DataGridView> при щелчке заголовка столбца автоматически сортируется по этому столбцу и отображается глиф, указывающий порядок сортировки.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|По умолчанию для столбцов, не являющихся текстовыми полей. Этот столбец можно отсортировать программно; Однако он не предназначен для сортировки, поэтому для глифа сортировки не резервируется место.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Этот столбец можно отсортировать программно, и для глифа сортировки зарезервировано пространство.|  
  
 Может потребоваться изменить режим сортировки для столбца, который по умолчанию <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> имеет значение, если он содержит значения, которые могут быть осмысленно упорядочены. Например, если имеется столбец базы данных, содержащий числа, представляющие состояния элементов, эти числа можно отобразить в виде соответствующих значков путем привязки столбца Image к столбцу базы данных. Затем числовые значения ячейки можно изменить на отображаемые значения изображения в обработчике <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> события. В этом случае, если задать <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> для <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> свойства значение, пользователи смогут сортировать столбец. Автоматическая сортировка позволяет пользователям группировать элементы, имеющие одинаковое состояние, даже если в состояниях, соответствующих числам, нет естественной последовательности. Столбцы флажков являются еще одним примером, где автоматическая сортировка полезна для группирования элементов в одном и том же состоянии.  
  
 Можно выполнить сортировку <xref:System.Windows.Forms.DataGridView> программными средствами по значениям в любом столбце или в нескольких столбцах независимо <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> от параметров. Программная сортировка полезна, если необходимо предоставить собственный пользовательский интерфейс для сортировки или реализовать пользовательскую сортировку. Предоставление собственного пользовательского интерфейса сортировки полезно, например, при установке <xref:System.Windows.Forms.DataGridView> режима выделения для включения выбора заголовка столбца. В этом случае, несмотря на то, что заголовки столбцов нельзя использовать для сортировки, все равно требуется, чтобы в заголовках отображался соответствующий глиф сортировки, поэтому <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> необходимо задать <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>для свойства значение.  
  
 Столбцы, для которых задан режим программной сортировки, не отображают глиф сортировки автоматически. Для этих столбцов необходимо самостоятельно отобразить глиф, задав <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> свойство. Это необходимо, если требуется гибкость при пользовательской сортировке. Например, при сортировке <xref:System.Windows.Forms.DataGridView> по нескольким столбцам может потребоваться отобразить несколько глифов сортировки или без глифа сортировки.  
  
 Хотя можно программно сортировать <xref:System.Windows.Forms.DataGridView> по любому столбцу, некоторые столбцы, например столбцы кнопок, могут не содержать значений, которые могут быть осмысленно упорядочены. Для этих столбцов <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> параметр свойства указывает, что он никогда не будет использоваться для сортировки, поэтому нет необходимости зарезервировать место в заголовке для глифа сортировки.  
  
 При сортировке можно определить как столбец сортировки, так и порядок сортировки, проверив значения <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> свойств и <xref:System.Windows.Forms.DataGridView.SortOrder%2A>. <xref:System.Windows.Forms.DataGridView> Эти значения не имеют смысла после пользовательской операции сортировки. Дополнительные сведения о пользовательской сортировке см. в разделе Настраиваемая сортировка далее в этом разделе.  
  
 При сортировке <xref:System.Windows.Forms.DataGridView> элемента управления, содержащего как связанные, так и несвязанные столбцы, значения в непривязанных столбцах не могут поддерживаться автоматически. Чтобы сохранить эти значения, необходимо реализовать <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> виртуальный режим, задав `true` свойству значение и обрабатывающее <xref:System.Windows.Forms.DataGridView.CellValueNeeded> события и <xref:System.Windows.Forms.DataGridView.CellValuePushed> . Дополнительные сведения см. в разделе [Практическое руководство. Реализуйте виртуальный режим в элементе управления](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView. Сортировка по несвязанным столбцам в связанном режиме не поддерживается.  
  
## <a name="programmatic-sorting"></a>Программная сортировка  
 Можно выполнить сортировку <xref:System.Windows.Forms.DataGridView> программным путем, <xref:System.Windows.Forms.DataGridView.Sort%2A> вызвав его метод.  
  
 `Sort(DataGridViewColumn,ListSortDirection)` Перегрузка <xref:System.Windows.Forms.DataGridView.Sort%2A> методапринимает<xref:System.Windows.Forms.DataGridViewColumn> в качестве параметров значение и перечисления.<xref:System.ComponentModel.ListSortDirection> Эта перегрузка полезна при сортировке по столбцам со значениями, которые могут быть осмысленно упорядочены, но которые не нужно настраивать для автоматической сортировки. При вызове этой перегрузки <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> и передаче столбца со <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>значением свойства, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> свойства и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> задаются автоматически, а соответствующий глиф сортировки отображается в заголовке столбца.  
  
> [!NOTE]
> Если элемент управления привязан к внешнему источнику данных путем <xref:System.Windows.Forms.DataGridView.DataSource%2A> установки свойства, `Sort(DataGridViewColumn,ListSortDirection)` перегрузка метода не работает для непривязанных столбцов. <xref:System.Windows.Forms.DataGridView> Кроме того, если <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство равно `true`, можно вызвать эту перегрузку только для связанных столбцов. Чтобы определить, привязан ли столбец к данным, проверьте <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> значение свойства. Сортировка непривязанных столбцов в связанном режиме не поддерживается.  
  
## <a name="custom-sorting"></a>Пользовательская сортировка  
 Можно настроить <xref:System.Windows.Forms.DataGridView> с `Sort(IComparer)` помощью перегрузки <xref:System.Windows.Forms.DataGridView.Sort%2A> метода или путем обработки <xref:System.Windows.Forms.DataGridView.SortCompare> события.  
  
 Перегрузка метода принимает экземпляр класса, который <xref:System.Collections.IComparer> реализует интерфейс в качестве параметра. `Sort(IComparer)` Эта перегрузка полезна, если нужно предоставить настраиваемую сортировку. Например, если значения в столбце не имеют естественного порядка сортировки или если естественный порядок сортировки не подходит. В этом случае нельзя использовать автоматическую сортировку, но по-прежнему необходимо, чтобы пользователи могли сортировать, щелкая заголовки столбцов. Эту перегрузку можно вызвать в обработчике для <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> события, если заголовки столбцов не используются для выбора.  
  
> [!NOTE]
> Перегрузка метода работает, только <xref:System.Windows.Forms.DataGridView> если элемент управления не привязан к <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> внешнему источнику данных, а свойство имеет `false`значение. `Sort(IComparer)` Чтобы настроить сортировку для столбцов, привязанных к внешнему источнику данных, необходимо использовать операции сортировки, предоставляемые источником данных. В виртуальном режиме необходимо предоставить собственные операции сортировки для несвязанных столбцов.  
  
 Чтобы использовать `Sort(IComparer)` перегрузку метода, необходимо создать собственный класс, <xref:System.Collections.IComparer> реализующий интерфейс. Этот интерфейс требует, чтобы ваш класс реализовал <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> метод, <xref:System.Windows.Forms.DataGridView> который передает <xref:System.Windows.Forms.DataGridViewRow> объекты в качестве входных данных при `Sort(IComparer)` вызове перегрузки метода. В этом случае можно вычислить правильный порядок строк на основе значений в любом столбце.  
  
 Перегрузка метода не <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> задает <xref:System.Windows.Forms.DataGridView.SortOrder%2A> Свойстваи,поэтомунеобходимовсегдаустанавливатьсвойстводлявыводаглифасортировки.<xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> `Sort(IComparer)`  
  
 В качестве альтернативы `Sort(IComparer)` перегрузке метода можно предоставить пользовательскую сортировку, реализовав обработчик <xref:System.Windows.Forms.DataGridView.SortCompare> для события. Это событие возникает, когда пользователи щелкают заголовки столбцов, настроенных для автоматической сортировки, или при `Sort(DataGridViewColumn,ListSortDirection)` вызове перегрузки <xref:System.Windows.Forms.DataGridView.Sort%2A> метода. Это событие возникает для каждой пары строк в элементе управления, что позволяет вычислить правильный порядок.  
  
> [!NOTE]
> Событие не происходит, <xref:System.Windows.Forms.DataGridView.DataSource%2A> если свойство задано или если <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство имеет `true`значение. <xref:System.Windows.Forms.DataGridView.SortCompare>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Сортировка данных в элементе управления DataGridView в Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Задание режимов сортировки для столбцов в элементе управления Windows Forms DataGridView](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Практическое руководство. Настройка сортировки в элементе управления Windows Forms DataGridView](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
