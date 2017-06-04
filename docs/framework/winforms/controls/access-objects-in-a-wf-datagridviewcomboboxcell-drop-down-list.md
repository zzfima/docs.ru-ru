---
title: "Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "поля со списком, доступ к объектам в раскрывающихся списках DataGridViewComboBoxCell"
  - "поля со списком, в элементе управления DataGridView"
  - "DataGridView - элемент управления [Windows Forms], доступ к объектам в ячейках с полями со списками"
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms
Аналогично элементу управления <xref:System.Windows.Forms.ComboBox> типы <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и <xref:System.Windows.Forms.DataGridViewComboBoxCell> позволяют добавлять в раскрывающиеся списки произвольные объекты.  С помощью этой функции можно отображать в раскрывающемся списке сложные состояния, не храня при этом соответствующие объекты в отдельной коллекции.  
  
 В отличие от элемента управления <xref:System.Windows.Forms.ComboBox> типы <xref:System.Windows.Forms.DataGridView> не имеют свойства <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> для восстановления текущего выбранного объекта.  Вместо этого необходимо задать для свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName> или <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName> имя свойства бизнес\-объекта.  При выборе объекта пользователем указанное свойство бизнес\-объекта присваивает значение свойству <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ячейки.  
  
 Чтобы извлечь бизнес\-объект с помощью значения ячейки, свойство `ValueMember` должно указывать на свойство, возвращающее ссылку на сам бизнес\-объект.  Таким образом, если нельзя управлять типом бизнес\-объекта, необходимо добавить такое свойство, расширив тип путем наследования.  
  
 В приведенных ниже процедурах демонстрируется заполнение раскрывающегося списка с использованием бизнес\-объектов, а также извлечение объектов с помощью свойства <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ячейки.  
  
### Чтобы добавить бизнес\-объекты в раскрывающийся список, выполните следующие действия:  
  
1.  Создайте новый элемент <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и заполните его коллекцию <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>.  Можно также задать для свойства столбца <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> коллекцию бизнес\-объектов.  Однако в этом случае нельзя добавить в раскрывающийся список значение "без присвоения", не создав соответствующий бизнес\-объект в коллекции.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  Установите свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> обозначает свойство бизнес\-объекта, отображаемое в раскрывающемся списке.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> обозначает свойство, которое возвращает ссылку на бизнес\-объект.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  Убедитесь, что тип бизнес\-объекта содержит свойство, возвращающее ссылку на текущий экземпляр.  Имя этого свойство должно иметь значение, назначенное свойству <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> на предыдущем этапе.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### Чтобы извлечь текущий выбранный бизнес\-объект, выполните следующие действия:  
  
-   Получите свойство <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ячейки и приведите его к типу бизнес\-объекта.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## Пример  
 В развернутом примере описано использование бизнес\-объектов в раскрывающемся списке.  В этом примере элемент управления <xref:System.Windows.Forms.DataGridView> связан с коллекцией объектов `Task`.  Каждый объект `Task` имеет свойство `AssignedTo`, указывающее объект `Employee`, которому назначена эта задача.  В столбце `Assigned To` отображается значение свойства `Name` для каждого назначенного сотрудника или значение "без присвоения", если свойство `Task.AssignedTo` имеет значение `null`.  
  
 Чтобы просмотреть работу этого примера, выполните следующие действия:  
  
1.  Измените назначения в столбце `Assigned To`, выбрав другие значения в раскрывающихся списках или нажав CTRL\+0 в ячейке с раскрывающимся списком.  
  
2.  Щелкните `Generate Report`, чтобы отобразить текущие назначения.  Этот пример демонстрирует, как изменение в столбце `Assigned To` автоматически меняет коллекцию `tasks`.  
  
3.  Нажмите кнопку `Request Status` для вызова метода `RequestStatus` текущего объекта `Employee` для этой строки.  Это показывает, что выбранный объект был успешно извлечен.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на сборки System и System.Windows.Forms.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ComboBox>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)