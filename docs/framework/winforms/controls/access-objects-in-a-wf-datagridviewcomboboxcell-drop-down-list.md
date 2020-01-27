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
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="85516-102">Практическое руководство. Доступ к объектам в раскрывающемся списке элемента управления DataGridViewComboBoxCell в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85516-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="85516-103">Как и элемент управления <xref:System.Windows.Forms.ComboBox>, типы <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и <xref:System.Windows.Forms.DataGridViewComboBoxCell> позволяют добавлять произвольные объекты в раскрывающиеся списки.</span><span class="sxs-lookup"><span data-stu-id="85516-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="85516-104">С помощью этой функции можно представить сложные состояния в раскрывающемся списке без необходимости хранить соответствующие объекты в отдельной коллекции.</span><span class="sxs-lookup"><span data-stu-id="85516-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="85516-105">В отличие от элемента управления <xref:System.Windows.Forms.ComboBox>, типы <xref:System.Windows.Forms.DataGridView> не имеют свойства <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> для получения текущего выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="85516-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="85516-106">Вместо этого необходимо задать для свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> имя свойства бизнес-объекта.</span><span class="sxs-lookup"><span data-stu-id="85516-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="85516-107">Когда пользователь делает выбор, указанное свойство бизнес-объекта задает свойство ячейки <xref:System.Windows.Forms.DataGridViewCell.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="85516-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="85516-108">Чтобы получить бизнес-объект через значение ячейки, свойство `ValueMember` должно указывать свойство, возвращающее ссылку на сам бизнес-объект.</span><span class="sxs-lookup"><span data-stu-id="85516-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="85516-109">Поэтому, если тип бизнес-объекта не находится под контролем, необходимо добавить такое свойство путем расширения типа посредством наследования.</span><span class="sxs-lookup"><span data-stu-id="85516-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="85516-110">В следующих процедурах показано, как заполнить раскрывающийся список бизнес-объектами и получить объекты с помощью свойства Cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="85516-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="85516-111">Добавление бизнес-объектов в раскрывающийся список</span><span class="sxs-lookup"><span data-stu-id="85516-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="85516-112">Создайте новый <xref:System.Windows.Forms.DataGridViewComboBoxColumn> и заполните его коллекцию <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="85516-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="85516-113">Кроме того, можно задать свойство Column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> для коллекции бизнес-объектов.</span><span class="sxs-lookup"><span data-stu-id="85516-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="85516-114">Однако в этом случае нельзя добавить "Неназначенное" в раскрывающийся список без создания соответствующего бизнес-объекта в коллекции.</span><span class="sxs-lookup"><span data-stu-id="85516-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="85516-115">Задайте свойства <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> и <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="85516-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="85516-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> указывает свойство бизнес-объекта, отображаемое в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="85516-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="85516-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> указывает свойство, возвращающее ссылку на бизнес-объект.</span><span class="sxs-lookup"><span data-stu-id="85516-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="85516-118">Убедитесь, что тип бизнес-объекта содержит свойство, возвращающее ссылку на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="85516-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="85516-119">Этому свойству необходимо присвоить значение, присвоенное <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="85516-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="85516-120">Получение выбранного в данный момент бизнес-объекта</span><span class="sxs-lookup"><span data-stu-id="85516-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="85516-121">Получите свойство <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ячейки и приведите его к типу бизнес-объекта.</span><span class="sxs-lookup"><span data-stu-id="85516-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="85516-122">Пример</span><span class="sxs-lookup"><span data-stu-id="85516-122">Example</span></span>  
 <span data-ttu-id="85516-123">В полном примере показано использование бизнес-объектов в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="85516-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="85516-124">В этом примере элемент управления <xref:System.Windows.Forms.DataGridView> привязан к коллекции объектов `Task`.</span><span class="sxs-lookup"><span data-stu-id="85516-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="85516-125">Каждый объект `Task` имеет свойство `AssignedTo`, указывающее на объект `Employee`, назначенный этой задаче в данный момент.</span><span class="sxs-lookup"><span data-stu-id="85516-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="85516-126">В столбце `Assigned To` отображается значение свойства `Name` для каждого назначенного сотрудника или значение "не назначено", если свойство `Task.AssignedTo` равно `null`.</span><span class="sxs-lookup"><span data-stu-id="85516-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="85516-127">Чтобы просмотреть поведение этого примера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="85516-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="85516-128">Измените назначения в столбце `Assigned To`, выбрав другие значения в раскрывающихся списках или нажав клавиши CTRL + 0 в ячейке с полем со списком.</span><span class="sxs-lookup"><span data-stu-id="85516-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="85516-129">Щелкните `Generate Report`, чтобы отобразить текущие назначения.</span><span class="sxs-lookup"><span data-stu-id="85516-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="85516-130">Это показывает, что изменение в столбце `Assigned To` автоматически обновляет коллекцию `tasks`.</span><span class="sxs-lookup"><span data-stu-id="85516-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="85516-131">Нажмите кнопку `Request Status`, чтобы вызвать метод `RequestStatus` текущего объекта `Employee` для этой строки.</span><span class="sxs-lookup"><span data-stu-id="85516-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="85516-132">Это показывает, что выбранный объект был успешно извлечен.</span><span class="sxs-lookup"><span data-stu-id="85516-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85516-133">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="85516-133">Compiling the Code</span></span>  
 <span data-ttu-id="85516-134">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="85516-134">This example requires:</span></span>  
  
- <span data-ttu-id="85516-135">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="85516-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85516-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="85516-136">See also</span></span>

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
- [<span data-ttu-id="85516-137">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85516-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
