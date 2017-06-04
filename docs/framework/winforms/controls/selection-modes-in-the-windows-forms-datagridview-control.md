---
title: "Режимы выделения содержимого элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "DataGridView - элемент управления [Windows Forms], режим выделения"
  - "выделенный фрагмент, режимы элемента управления DataGridView"
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Режимы выделения содержимого элемента управления DataGridView в Windows Forms
Иногда необходимо, чтобы приложение выполняло действия в зависимости от выбранного пользователем объекта внутри элемента управления <xref:System.Windows.Forms.DataGridView>.  В зависимости от действий может потребоваться запрет выбора некоторых типов объектов.  Например, предположим, что приложение выполняет печать отчета по выделенной в данный момент записи.  В этом случае, элемент управления <xref:System.Windows.Forms.DataGridView> может потребоваться настроить таким образом, чтобы при щелчке в любой области строки выделялась строка целиком и только одна строка одновременно.  
  
 Объекты, выбор которых разрешается, можно указать при помощи свойства <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName>, присвоив ему одно из следующих значений перечисления <xref:System.Windows.Forms.DataGridViewSelectionMode>.  
  
|Значение DataGridViewSelectionMode|Описание|  
|----------------------------------------|--------------|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Выделение ячейки по щелчку кнопкой мыши.  Строки и столбцы выделить нельзя.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Выделение ячейки по щелчку кнопкой мыши.  Выделение столбца целиком по щелчку на заголовке столбца.  Заголовки столбцов нельзя использовать для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Выделение столбца целиком по щелчку на ячейке или заголовке столбца.  Заголовки столбцов нельзя использовать для сортировки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Выделение строки целиком по щелчку на ячейке или заголовке строки.|  
|<xref:System.Windows.Forms.DataGridViewSelectionMode>|Режим выделения по умолчанию.  Выделение ячейки по щелчку кнопкой мыши.  Выделение строки целиком по щелчку на заголовке строки.|  
  
> [!NOTE]
>  Изменение режима выделения во время выполнения автоматически снимает текущее выделение.  
  
 По умолчанию пользователи могут выделять несколько строк, столбцов или ячеек путем перетаскивания курсора мыши, расширения или изменения области выделения при нажатой клавише CTRL или SHIFT, или по щелчку заголовка верхней левой ячейки для выделения всех строк в элементе управления.  Чтобы запретить такое выделение, свойству <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> следует присвоить значение `false`.  
  
 Режимы <xref:System.Windows.Forms.DataGridViewSelectionMode> и <xref:System.Windows.Forms.DataGridViewSelectionMode> позволяют удалять строки путем их выделения и нажатия клавиши DELETE.  Пользователи могут удалить строки только в том случае, если текущая ячейка не в режиме редактирования, свойство <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> имеет значение `true`, а основной источник данных поддерживает удаление строк пользователем.  Обратите внимание, что эти параметры не препятствуют удалению строк программным образом.  
  
## Программное выделение  
 Текущий режим выделения ограничивает возможности программного выделения, равно как и выделения пользователем.  Текущее выделение можно изменить программно, установив свойство `Selected` любых ячеек, строк или столбцов в элементе управления <xref:System.Windows.Forms.DataGridView>.  Кроме того, в зависимости от режима выделения можно также выделить все ячейки в элементе управления при помощи метода <xref:System.Windows.Forms.DataGridView.SelectAll%2A>.  Чтобы снять выделение, используйте метод <xref:System.Windows.Forms.DataGridView.ClearSelection%2A>.  
  
 Если свойство <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> имеет значение `true`, элементы <xref:System.Windows.Forms.DataGridView> можно добавить в область выделения или исключить их из нее, изменив свойство `Selected` элемента.  В противном случае, присвоение свойству `Selected` значения `true` для одного элемента приведет к автоматическому исключению элементов из выделения.  
  
 Обратите внимание, что изменение значения свойства <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> не приводит к изменению текущего выделения.  
  
 Набор выделенных ячеек, строк или столбцов можно извлечь при помощи свойств <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> и <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.  Если в элементе управления выделены все ячейки, обращение к этим свойствам будет неэффективным.  Чтобы избежать снижения производительности в этом случае, сначала используйте метод <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>.  Кроме того, обращение к этим коллекциям для определения числа выделенных ячеек, строк или столбцов может также оказаться неэффективным.  Вместо этого следует использовать метод <xref:System.Windows.Forms.DataGridView.GetCellCount%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A> или <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A>, подставляющий значение <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
> [!TIP]
>  Пример кода, демонстрирующий программное использование выделенных ячеек, см. в обзоре класса <xref:System.Windows.Forms.DataGridView>.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridViewSelectionMode>   
 [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Определение режима выделения для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)