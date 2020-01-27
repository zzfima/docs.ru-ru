---
title: Доступ к объектам в раскрывающемся списке DataGridViewComboBoxCell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746309"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms
Как и элемент управления <xref:System.Windows.Forms.ComboBox>, типы <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и <xref:System.Windows.Forms.DataGridViewComboBoxCell> позволяют добавлять произвольные объекты в раскрывающиеся списки. С помощью этой функции можно представить сложные состояния в раскрывающемся списке без необходимости хранить соответствующие объекты в отдельной коллекции.  
  
 В отличие от элемента управления <xref:System.Windows.Forms.ComboBox>, типы <xref:System.Windows.Forms.DataGridView> не имеют свойства <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> для получения текущего выбранного объекта. Вместо этого необходимо задать для свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> имя свойства бизнес-объекта. Когда пользователь делает выбор, указанное свойство бизнес-объекта задает свойство ячейки <xref:System.Windows.Forms.DataGridViewCell.Value%2A>.  
  
 Чтобы получить бизнес-объект через значение ячейки, свойство `ValueMember` должно указывать свойство, возвращающее ссылку на сам бизнес-объект. Поэтому, если тип бизнес-объекта не находится под контролем, необходимо добавить такое свойство путем расширения типа посредством наследования.  
  
 В следующих процедурах показано, как заполнить раскрывающийся список бизнес-объектами и получить объекты с помощью свойства Cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A>.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Добавление бизнес-объектов в раскрывающийся список  
  
1. Создайте новый <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и заполните его коллекцию <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>. Кроме того, можно задать свойство Column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> для коллекции бизнес-объектов. Однако в этом случае нельзя добавить "Неназначенное" в раскрывающийся список без создания соответствующего бизнес-объекта в коллекции.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Задайте свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> указывает свойство бизнес-объекта, отображаемое в раскрывающемся списке. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> указывает свойство, возвращающее ссылку на бизнес-объект.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Убедитесь, что тип бизнес-объекта содержит свойство, возвращающее ссылку на текущий экземпляр. Этому свойству необходимо присвоить значение, присвоенное <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> на предыдущем шаге.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Получение выбранного в данный момент бизнес-объекта  
  
- Получите свойство <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ячейки и приведите его к типу бизнес-объекта.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Пример  
 В полном примере показано использование бизнес-объектов в раскрывающемся списке. В этом примере элемент управления <xref:System.Windows.Forms.DataGridView> привязан к коллекции объектов `Task`. Каждый объект `Task` имеет свойство `AssignedTo`, указывающее на объект `Employee`, назначенный этой задаче в данный момент. В столбце `Assigned To` отображается значение свойства `Name` для каждого назначенного сотрудника или значение "не назначено", если свойство `Task.AssignedTo` равно `null`.  
  
 Чтобы просмотреть поведение этого примера, выполните следующие действия.  
  
1. Измените назначения в столбце `Assigned To`, выбрав другие значения в раскрывающихся списках или нажав клавиши CTRL + 0 в ячейке с полем со списком.  
  
2. Щелкните `Generate Report`, чтобы отобразить текущие назначения. Это показывает, что изменение в столбце `Assigned To` автоматически обновляет коллекцию `tasks`.  
  
3. Нажмите кнопку `Request Status`, чтобы вызвать метод `RequestStatus` текущего объекта `Employee` для этой строки. Это показывает, что выбранный объект был успешно извлечен.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System и System.Windows.Forms;  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
