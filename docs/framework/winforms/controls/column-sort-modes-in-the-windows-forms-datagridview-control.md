---
title: "Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "таблицы данных, режимы сортировки"
  - "DataGridView - элемент управления [Windows Forms], режим сортировки"
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms
К столбцам <xref:System.Windows.Forms.DataGridView> применимы три режима сортировки.  Режим сортировки для каждого столбца определяется с помощью свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> столбца, которому можно присвоить одно из значений перечисления <xref:System.Windows.Forms.DataGridViewColumnSortMode>.  
  
|Значение `DataGridViewColumnSortMode`|Описание|  
|-------------------------------------------|--------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Принимается по умолчанию для столбцов текстовых полей.  Если заголовки столбцов не используются для выделения, щелчок мышью по заголовку столбца приводит к автоматической сортировке <xref:System.Windows.Forms.DataGridView> по данному столбцу и выводу глифа с указанием порядка сортировки.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Принимается по умолчанию для столбцов, содержащих не текстовые поля.  Сортировку таких столбцов можно реализовать программным путем. Однако они не предназначены для сортировки, и место для глифа сортировки не предусматривается.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Сортировку таких столбцов можно реализовать программным путем. Место для глифа сортировки предусматривается.|  
  
 Для столбца, который по умолчанию имеет значение <xref:System.Windows.Forms.DataGridViewColumnSortMode>, может потребоваться изменить режим сортировки, если он содержит значения, допускающие осмысленную сортировку.  Например, если в базе данных имеется столбец с числами, указывающими на состояние элементов, эти числа можно отображать в виде соответствующих значков, привязав к этому столбцу базы данных столбец с изображениями.  Далее можно преобразовать числовые значения ячеек в графические значения в обработчике события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  В этом случае после присвоения свойству <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значения <xref:System.Windows.Forms.DataGridViewColumnSortMode> пользователи получат возможность производить сортировку столбца.  Автоматическая сортировка позволяет пользователям группировать элементы, имеющие одинаковое состояние, даже если соответствующие состояниям числа не образуют натуральный ряд.  Столбцы флажков представляют собой еще один пример целесообразности использования автоматической сортировки для группировки элементов с одинаковым состоянием.  
  
 Программная сортировка <xref:System.Windows.Forms.DataGridView> может осуществляться по значениям любого из столбцов или сразу по нескольким столбцам вне зависимости от параметров свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.  Программная сортировка может использоваться, если необходимо предоставить собственный пользовательский интерфейс для сортировки или реализовать особый механизм сортировки.  Создание собственного пользовательского интерфейса сортировки может оказаться необходимым, например, при использовании в качестве режима выделения для элемента управления <xref:System.Windows.Forms.DataGridView> выделения по заголовку столбца.  В этом случае, хотя заголовки столбцов и не могут использоваться для сортировки, необходимо все же, чтобы в заголовках отображался соответствующий глиф сортировки. Поэтому свойству <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> необходимо присвоить значение <xref:System.Windows.Forms.DataGridViewColumnSortMode>.  
  
 Столбцы, для которых задан программный режим сортировки, не отображают глиф сортировки автоматически.  Отображение глифа для таких столбцов необходимо настроить самостоятельно путем задания значения для свойства <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>.  Это необходимо для достижения гибкости при использовании пользовательской сортировки.  Например, при сортировке <xref:System.Windows.Forms.DataGridView> по нескольким столбцам, может возникнуть необходимость в отображении нескольких или ни одного глифа сортировки.  
  
 Хотя программная сортировка <xref:System.Windows.Forms.DataGridView> может производиться по любому столбцу, некоторые столбцы, например столбцы кнопок, могут не содержать значений, которые могут быть осмысленно упорядочены.  Для подобных столбцов присвоение свойству <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значения <xref:System.Windows.Forms.DataGridViewColumnSortMode> указывает на то, что они не будут использоваться для сортировки и, соответственно, место для глифа сортировки резервировать не нужно.  
  
 При сортировке элемента управления <xref:System.Windows.Forms.DataGridView> можно определить как столбец сортировки, так и порядок сортировки по значениям свойств <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A>.  Эти значения не имеют смысла после проведения пользовательской сортировки.  Дополнительные сведения о пользовательской сортировке см. в разделе "Пользовательская сортировка" ниже.  
  
 При сортировке элемента управления <xref:System.Windows.Forms.DataGridView>, содержащего как связанные, так и несвязанные столбцы, автоматическое сохранение значений в несвязанных столбцах невозможно.  Для сохранения этих значений следует применить виртуальный режим путем присвоения свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> значения `true` и обработки событий <xref:System.Windows.Forms.DataGridView.CellValueNeeded> и <xref:System.Windows.Forms.DataGridView.CellValuePushed>.  Дополнительные сведения см. в разделе [Практическое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  Сортировка по несвязанным столбцам в связанном режиме не поддерживается.  
  
## Программная сортировка  
 Сортировка элемента управления <xref:System.Windows.Forms.DataGridView> может производиться программным способом путем вызова метода <xref:System.Windows.Forms.DataGridView.Sort%2A>.  
  
 Перегрузка `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> принимает в качестве параметров значения перечислений <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.ComponentModel.ListSortDirection>.  Эта перегрузка может использоваться при сортировке столбцов, содержащих значения, которые могут быть осмысленно упорядочены, но для которых нежелательно использовать автоматическую сортировку.  При вызове этой перегрузки и передаче столбца со значением <xref:System.Windows.Forms.DataGridViewColumnSortMode?displayProperty=fullName> свойства <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> значения свойств <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A> задаются автоматически, а в заголовке столбца появляется соответствующий глиф сортировки.  
  
> [!NOTE]
>  Если элемент управления <xref:System.Windows.Forms.DataGridView> связан с внешним источником данных путем задания свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A>, перегрузка метода `Sort(DataGridViewColumn,ListSortDirection)` не работает для несвязанных столбцов.  Кроме того, если свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`, вызов этой перегрузки возможен только для связанных столбцов.  Определить, является ли столбец связанным, можно исходя из значения свойства <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>.  Сортировка несвязанных столбцов в связанном режиме не поддерживается.  
  
## Пользовательская сортировка  
 Элемент управления <xref:System.Windows.Forms.DataGridView> может настраиваться путем использования перегрузки `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> или путем обработки события <xref:System.Windows.Forms.DataGridView.SortCompare>.  
  
 Перегрузка метода `Sort(IComparer)` принимает в качестве параметра экземпляр класса, который реализует интерфейс <xref:System.Collections.IComparer>.  Эта перегрузка может использоваться, если необходимо обеспечить пользовательский механизм сортировки, например, когда значения в столбце не имеют естественного порядка сортировки или же естественный порядок сортировки непригоден.  В этом случае использование автоматической сортировки невозможно, однако сортировка путем щелчка мышью по заголовкам столбцов может быть желательна.  Если заголовки столбцов не используются для выделения, эту перегрузку можно вызвать в обработчике события <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>.  
  
> [!NOTE]
>  Перегрузка метода `Sort(IComparer)` работает, только если элемент управления <xref:System.Windows.Forms.DataGridView> не связан с внешним источником данных, а свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `false`.  Для настройки сортировки для столбцов, связанных с внешним источником данных, следует воспользоваться операциями сортировки, которые поддерживаются этим источником данных.  В виртуальном режиме операции сортировки для несвязанных столбцов необходимо обеспечить самостоятельно.  
  
 Для использования перегрузки метода `Sort(IComparer)` необходимо создать собственный класс, реализующий интерфейс <xref:System.Collections.IComparer>.  В соответствии с требованиями этого интерфейса в классе должен быть реализован метод <xref:System.Collections.IComparer.Compare%2A?displayProperty=fullName>, которому <xref:System.Windows.Forms.DataGridView> передает в качестве входных данных объекты <xref:System.Windows.Forms.DataGridViewRow> при вызове перегрузки метода `Sort(IComparer)`.  Благодаря этому правильный порядок строк может быть рассчитан на основании значений, содержащихся в любом из столбцов.  
  
 Перегрузка метода `Sort(IComparer)` не задает значения свойств <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> и <xref:System.Windows.Forms.DataGridView.SortOrder%2A>, поэтому для отображения глифа сортировки необходимо задать значение свойства <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>.  
  
 В качестве альтернативы перегрузке метода `Sort(IComparer)` пользовательскую сортировку можно реализовать путем использования обработчика события <xref:System.Windows.Forms.DataGridView.SortCompare>.  Это событие наступает при щелчке мышью по заголовкам столбцов, для которых настроена автоматическая сортировка, или при вызове перегрузки `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>.  Событие генерируется для каждой пары строк в элементе управления, что дает возможность определить их правильный порядок.  
  
> [!NOTE]
>  Событие <xref:System.Windows.Forms.DataGridView.SortCompare> не возникает, если задано свойство <xref:System.Windows.Forms.DataGridView.DataSource%2A> или если свойство <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> имеет значение `true`.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>   
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)   
 [Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)