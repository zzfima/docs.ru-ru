---
title: "Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d0f4eb14fbb459f6844053507d1eb4f0a46cede3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms
Как <xref:System.Windows.Forms.ComboBox> управления <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и <xref:System.Windows.Forms.DataGridViewComboBoxCell> типы позволяют добавлять произвольные объекты в свой список раскрывающегося списка. С помощью этой функции может представлять сложных состояний в раскрывающемся списке без сохранения соответствующие объекты в отдельной коллекции.  
  
 В отличие от <xref:System.Windows.Forms.ComboBox> управления <xref:System.Windows.Forms.DataGridView> типы не имеют <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> свойство для извлечения текущего выбранного объекта. Вместо этого необходимо задать <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> на имя свойства бизнес-объекта. Когда пользователь выбирает, заданное свойство бизнес-объекта задает ячейку <xref:System.Windows.Forms.DataGridViewCell.Value%2A> свойство.  
  
 Для получения бизнес-объекта по значению ячейки, `ValueMember` свойство должно указывать свойство, возвращающее ссылку на сам бизнес-объект. Таким образом Если тип бизнес-объекта не под вашим управлением, необходимо добавить такое свойство, расширив тип путем наследования.  
  
 Следующие процедуры демонстрируют, как для заполнения раскрывающегося списка с бизнес-объектов и извлечение объектов с помощью ячейки <xref:System.Windows.Forms.DataGridViewCell.Value%2A> свойство.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Добавление бизнес-объектов в раскрывающемся списке  
  
1.  Создайте новый <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и заполнить его <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> коллекции. Кроме того, можно задать столбец <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> коллекция бизнес-объектов. В этом случае тем не менее, вы не может добавить «неназначенные» в раскрывающемся списке без создания соответствующего бизнес-объекта в коллекции.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  Задайте свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>Указывает свойство бизнес-объекта для отображения в раскрывающемся списке. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>обозначает свойство, которое возвращает ссылку на бизнес-объекта.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  Убедитесь, что ваш тип бизнес-объекта содержит свойство, возвращающее ссылку на текущий экземпляр. Это свойство должно с именем, и значение, присваиваемое <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> на предыдущем шаге.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Для получения текущего выбранного бизнес-объекта  
  
-   Получить ячейку <xref:System.Windows.Forms.DataGridViewCell.Value%2A> свойство и приведите его тип бизнес-объекта.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Пример  
 Полный пример демонстрирует использование бизнес-объектов в раскрывающемся списке. В примере <xref:System.Windows.Forms.DataGridView> элемент управления привязан к коллекции `Task` объектов. Каждый `Task` объект имеет `AssignedTo` свойство, которое показывает `Employee` объекта, назначенный этой задачи. `Assigned To` Столбец отображает `Name` назначить значение свойства для каждого сотрудника, или «неназначенные», если `Task.AssignedTo` значение свойства `null`.  
  
 Чтобы просмотреть работу этого примера, выполните следующие действия:  
  
1.  Измените назначения в `Assigned To` столбца путем выбора различных значений из раскрывающихся списков или нажав клавиши CTRL + 0 в ячейке с раскрывающимся списком.  
  
2.  Щелкните `Generate Report` для отображения текущих назначений. Этот пример демонстрирует изменение `Assigned To` автоматически обновляет столбец `tasks` коллекции.  
  
3.  Нажмите кнопку `Request Status` кнопку, чтобы вызвать `RequestStatus` метод текущего `Employee` объекта для этой строки. Это показывает, что выбранный объект был успешно извлечен.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms;  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ComboBox>  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
