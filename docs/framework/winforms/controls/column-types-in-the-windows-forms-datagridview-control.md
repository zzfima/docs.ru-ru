---
title: "Типы столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], типы"
  - "таблицы данных, столбцы"
  - "DataGridView - элемент управления [Windows Forms], типы столбцов"
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Типы столбцов элемента управления DataGridView в Windows Forms
В элементе управления <xref:System.Windows.Forms.DataGridView> используется несколько типов столбцов, использующихся для отображения данных и позволяющих пользователям изменять или добавлять данные.  
  
 При связывании элемента управления <xref:System.Windows.Forms.DataGridView> и присвоении свойству <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> значения `true` столбцы создаются автоматически с использованием типов столбцов по умолчанию, соответствующих типам данных в связанном источнике данных.  
  
 Также существует возможность самостоятельного создания экземпляров любых классов столбцов и добавления их в коллекцию, возвращаемую свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>.  Эти экземпляры могут использоваться как несвязанные столбцы, или же можно привязать их вручную.  Привязка столбцов вручную может использоваться, например, при необходимости замены автоматически созданного столбца столбцом другого типа.  
  
 В следующей таблице приводится описание различных классов столбцов, которые могут использоваться в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
|Класс|Описание|  
|-----------|--------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|Используется с текстовыми значениями.  Создается автоматически при привязке к числовым и строковым типам данных.|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|Используется со значениями типа <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState>.  Создается автоматически при привязке к значениям, имеющим эти типы.|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|Используется для отображения изображений.  Создается автоматически при привязке к байтовым массивам, объектам <xref:System.Drawing.Image> или <xref:System.Drawing.Icon>.|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|Используется для отображения кнопок в ячейках.  Не может создаваться автоматически при выполнении привязки.  Обычно используется в качестве несвязанного столбца.|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|Используется для отображения в ячейках раскрывающихся списков.  Не может создаваться автоматически при выполнении привязки.  Обычно связывание производится вручную.|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|Используется для отображения ссылок в ячейках.  Не может создаваться автоматически при выполнении привязки.  Обычно связывание производится вручную.|  
|Пользовательский тип столбцов|Существует возможность создания собственных классов столбцов путем наследования класса <xref:System.Windows.Forms.DataGridViewColumn> или любого из его производных классов. Это позволяет настраивать внешний вид столбцов, их поведение, а также размещать в них элементы управления.  Дополнительные сведения см. в разделе [Практическое руководство. Дополнительные возможности управления внешним видом и поведением ячеек и столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).|  
  
 Эти типы столбцов описаны более подробно в следующих разделах.  
  
## DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn> — это тип столбцов общего назначения, предназначенный для значений, которые могут быть представлены в виде текста, например числовые и строковые значения.  В режиме редактирования в активной ячейке отображается элемент управления <xref:System.Windows.Forms.TextBox>, дающий пользователю возможность изменять значение ячейки.  
  
 При отображении значения ячеек автоматически приводятся к строковому типу.  Вводимые или изменяемые пользователем значения автоматически анализируются и преобразуются в значение ячейки соответствующего типа.  Управление этими преобразованиями может осуществляться путем обработки событий <xref:System.Windows.Forms.DataGridView.CellFormatting> и <xref:System.Windows.Forms.DataGridView.CellParsing> элемента управления <xref:System.Windows.Forms.DataGridView>.  
  
 Тип данных для значений ячеек данного столбца определяется свойством <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> столбца.  
  
## DataGridViewCheckBoxColumn  
 Объект <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> используется со значениями <xref:System.Boolean> и <xref:System.Windows.Forms.CheckState>.  Значения <xref:System.Boolean> отображаются как флажки с двумя или тремя состояниями в зависимости от значения свойства <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A>.  Если столбец привязан к значениям типа <xref:System.Windows.Forms.CheckState>, свойство <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> по умолчанию имеет значение `true`.  
  
 Обычно ячейки с флажками предназначены либо для хранения данных, как и другие типы ячеек, либо для выполнения массовых операций.  Если необходимо обеспечить мгновенную реакцию на щелчок мышью ячейки с флажком, можно воспользоваться обработкой события <xref:System.Windows.Forms.DataGridView.CellClick>, однако это событие происходит до обновления значения ячейки.  Если в момент выполнения щелчка мышью уже необходимо новое значение, можно вычислить ожидаемое значение, исходя из текущего значения.  В качестве альтернативы можно сразу же зафиксировать изменение и выполнить обработку события <xref:System.Windows.Forms.DataGridView.CellValueChanged>, чтобы обеспечить соответствующую реакцию на это изменение.  Чтобы зафиксировать изменение по щелчку ячейки, следует обработать событие <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged>.  Если данная ячейка содержит флажок вызовите в этом обработчике метод <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> и передайте ему значение <xref:System.Windows.Forms.DataGridViewDataErrorContexts>.  
  
## DataGridViewImageColumn  
 Тип столбцов <xref:System.Windows.Forms.DataGridViewImageColumn> используется для отображения изображений.  Заполнение столбцов изображений может производиться автоматически с помощью источника данных, вручную \(для несвязанных столбцов\) или динамически с помощью обработчика события <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 Для автоматического заполнения столбцов изображений из источника данных могут использоваться байтовые массивы различных графических форматов, включая любые форматы, поддерживаемые классом <xref:System.Drawing.Image>, а также графический формат OLE, используемый в Microsoft® Access и демонстрационной базе данных "Northwind".  
  
 Заполнение столбцов изображений вручную может использоваться для обеспечения функциональности, аналогичной функциональности типа <xref:System.Windows.Forms.DataGridViewButtonColumn>, но с нестандартным внешним видом.  Реакция на щелчок мыши в области ячейки с изображением может быть определена с помощью обработчика события <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>.  
  
 Заполнение ячеек столбца изображений с помощью обработчика события <xref:System.Windows.Forms.DataGridView.CellFormatting> может использоваться при необходимости отображения изображений в соответствии с вычисленным значениями либо отображения значений, не являющихся изображениями.  Например, имеется столбец "Risk" со строковыми значениями, такими как `"high"`, `"middle"` и `"low"`, которые нужно представить в виде значков.  Другой пример — столбец "Image", содержащий сведения о расположении изображений, которые должны быть загружены, а не сам двоичный код изображений.  
  
## DataGridViewButtonColumn  
 Тип столбцов <xref:System.Windows.Forms.DataGridViewButtonColumn> позволяет отображать столбцы ячеек, содержащих кнопки.  С помощью таких столбцов можно упростить для пользователей выполнение некоторых действий над записями, таких как размещение заказа или вывод дочерних записей в отдельном окне.  
  
 Столбцы кнопок не могут создаваться автоматически при связывании элемента управления <xref:System.Windows.Forms.DataGridView>.  Использование столбцов кнопок возможно только путем их создания вручную и добавления их в коллекцию, возвращаемую свойством <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>.  
  
 Реакция на щелчок мышью по кнопке, размещенной в ячейке, может быть определена с помощью обработчика события <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>.  
  
## DataGridViewComboBoxColumn  
 Тип столбцов <xref:System.Windows.Forms.DataGridViewComboBoxColumn> позволяет отображать столбцы ячеек, содержащих раскрывающиеся списки.  Такие столбцы могут использоваться в случае, если ячейки для ввода данных могут иметь только некоторые определенные значения. Примером может служить столбец "Category" таблицы "Products" в демонстрационной базе данных "Northwind".  
  
 Заполнение раскрывающегося списка, используемого для всех ячеек столбца, производится аналогично заполнению раскрывающегося списка <xref:System.Windows.Forms.ComboBox>. Оно может выполняться либо вручную с помощью коллекции, возвращаемой свойством <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>, либо путем привязки к источнику данных посредством свойств <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.  Дополнительные сведения см. в разделе [Элемент управления ComboBox](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md).  
  
 Фактические значения ячеек можно привязать к источнику данных, используемому элементом управления <xref:System.Windows.Forms.DataGridView>, путем задания свойства <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> объекта <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=fullName>.  
  
 Столбцы типа "поле со списком" не могут создаваться автоматически при связывании элемента управления <xref:System.Windows.Forms.DataGridView>.  Использование столбцов типа "поле со списком" возможно только путем их создания вручную и добавления их в коллекцию, возвращаемую свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
## DataGridViewLinkColumn  
 Тип столбцов <xref:System.Windows.Forms.DataGridViewLinkColumn> позволяет отображать столбцы ячеек, содержащих гиперссылки.  Они могут использоваться в том случае, если источник данных содержит URL\-адреса в качестве значений, или как альтернатива столбцам кнопок для обеспечения особого поведения, например открытия окна с дочерними записями.  
  
 Столбцы ссылок не могут создаваться автоматически при связывании элемента управления <xref:System.Windows.Forms.DataGridView>.  Использование столбцов ссылок возможно только путем их создания вручную и добавления их в коллекцию, возвращаемую свойством <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
 Реакция на щелчок мышью по ссылке в ячейке может быть определена с помощью обработчика события <xref:System.Windows.Forms.DataGridView.CellContentClick>.  Это событие отличается от событий <xref:System.Windows.Forms.DataGridView.CellClick> и <xref:System.Windows.Forms.DataGridView.CellMouseClick>, которые наступают при щелчке мышью в любом месте в пределах ячейки.  
  
 Класс <xref:System.Windows.Forms.DataGridViewLinkColumn> имеет несколько свойств, предназначенных для изменения вида ссылок перед нажатием мышью, в момент нажатия и после него.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewButtonColumn>   
 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewImageColumn>   
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewLinkColumn>   
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Работа со столбцами изображений в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)   
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)