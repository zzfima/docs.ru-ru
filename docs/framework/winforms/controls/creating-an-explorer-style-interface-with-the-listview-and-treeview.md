---
title: Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "69658573"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="dfbe9-102">Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="dfbe9-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="dfbe9-103">Одним из преимуществ Visual Studio является возможность создания профессионально оформленных Windows Forms приложений в течение короткого промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="dfbe9-104">Распространенным сценарием является создание пользовательского интерфейса с <xref:System.Windows.Forms.ListView> элементами управления и <xref:System.Windows.Forms.TreeView> , которые похожи на проводник Windows в операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="dfbe9-105">Проводник Windows отображает иерархическую структуру файлов и папок на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="dfbe9-106">Создание формы, содержащей элемент управления ListView и TreeView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-106">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="dfbe9-107">В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="dfbe9-108">В диалоговом окне **Новый проект** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-108">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="dfbe9-109">В категории выберите либо **Visual Basic** , либо **визуальный C#** элемент.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-109">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="dfbe9-110">В списке шаблонов выберите **Windows Forms приложение**.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-110">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="dfbe9-111">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-111">Click **OK**.</span></span> <span data-ttu-id="dfbe9-112">Будет создан новый проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-112">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="dfbe9-113">Добавьте в форму <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Fill>элемент управления и задайте для его свойства значение. <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="dfbe9-113">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="dfbe9-114">Добавьте именованный `imageList1` элемент в форму и используйте окно свойств, чтобы добавить два изображения: изображение папки и изображение документа в указанном порядке. <xref:System.Windows.Forms.ImageList></span><span class="sxs-lookup"><span data-stu-id="dfbe9-114">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="dfbe9-115">Добавьте элемент управления с `treeview1` именем в форму и разместите его в левой <xref:System.Windows.Forms.SplitContainer> части элемента управления. <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="dfbe9-115">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="dfbe9-116">В окно свойств `treeView1` выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-116">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="dfbe9-117">Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-117">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="dfbe9-118">Задайте свойству <xref:System.Windows.Forms.TreeView.ImageList%2A> значение `imagelist1.`</span><span class="sxs-lookup"><span data-stu-id="dfbe9-118">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="dfbe9-119">Добавьте элемент управления с `listView1` именем в форму и разместите его в правой <xref:System.Windows.Forms.SplitContainer> части элемента управления. <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="dfbe9-119">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="dfbe9-120">В окно свойств `listview1` выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-120">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="dfbe9-121">Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-121">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="dfbe9-122">Задайте для свойства <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-122">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="dfbe9-123">Откройте редактор коллекции колумнхеадер, нажав кнопку с многоточием (![...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) в <xref:System.Windows.Forms.ListView.Columns%2A> свойстве **.**</span><span class="sxs-lookup"><span data-stu-id="dfbe9-123">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="dfbe9-124">Добавьте три столбца и задайте для <xref:System.Windows.Forms.ColumnHeader.Text%2A> `Name`них свойства, `Type`и `Last Modified`соответственно.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-124">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="dfbe9-125">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-125">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="dfbe9-126">Задайте свойству <xref:System.Windows.Forms.ListView.SmallImageList%2A> значение `imageList1.`</span><span class="sxs-lookup"><span data-stu-id="dfbe9-126">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="dfbe9-127">Реализуйте код, чтобы заполнить <xref:System.Windows.Forms.TreeView> узлы и подузлы.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-127">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="dfbe9-128">Добавьте этот код в `Form1` класс.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-128">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="dfbe9-129">Поскольку в предыдущем коде используется пространство имен System.IO, добавьте соответствующий оператор using или Import в верхней части формы.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-129">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="dfbe9-130">Вызовите метод Set-up из предыдущего шага в конструкторе формы или <xref:System.Windows.Forms.Form.Load> методе обработки событий.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-130">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="dfbe9-131">Добавьте этот код в конструктор формы.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-131">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="dfbe9-132">Обработайте `treeview1` событиедля`listview1` и реализуйте код, который заполняется содержимым узла при щелчке узла. <xref:System.Windows.Forms.TreeView.NodeMouseClick></span><span class="sxs-lookup"><span data-stu-id="dfbe9-132">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="dfbe9-133">Добавьте этот код в `Form1` класс.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-133">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="dfbe9-134">Если используется C#, убедитесь, что у вас есть <xref:System.Windows.Forms.TreeView.NodeMouseClick> событие, связанное с методом обработки событий.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-134">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="dfbe9-135">Добавьте этот код в конструктор формы.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-135">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="dfbe9-136">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="dfbe9-136">Testing the Application</span></span>

<span data-ttu-id="dfbe9-137">Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-137">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="dfbe9-138">Тестирование формы</span><span class="sxs-lookup"><span data-stu-id="dfbe9-138">To test the form</span></span>

- <span data-ttu-id="dfbe9-139">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-139">Press F5 to run the application.</span></span>

     <span data-ttu-id="dfbe9-140">Вы увидите разделенную форму, содержащую <xref:System.Windows.Forms.TreeView> элемент управления, который отображает каталог проекта слева, <xref:System.Windows.Forms.ListView> и элемент управления с правой стороны с тремя столбцами.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-140">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="dfbe9-141">Можно просмотреть <xref:System.Windows.Forms.TreeView> , выбрав узлы каталога, <xref:System.Windows.Forms.ListView> и заполнится содержимым выбранного каталога.</span><span class="sxs-lookup"><span data-stu-id="dfbe9-141">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dfbe9-142">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="dfbe9-142">Next Steps</span></span>

<span data-ttu-id="dfbe9-143">Это приложение предоставляет пример того, как можно использовать <xref:System.Windows.Forms.TreeView> вместе элементы управления и. <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="dfbe9-143">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="dfbe9-144">Дополнительные сведения об этих элементах управления см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="dfbe9-144">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="dfbe9-145">Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dfbe9-145">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="dfbe9-146">Практическое руководство. Добавление возможностей поиска в элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-146">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="dfbe9-147">Практическое руководство. Присоединение контекстного меню к узлу TreeView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-147">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="dfbe9-148">См. также</span><span class="sxs-lookup"><span data-stu-id="dfbe9-148">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="dfbe9-149">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-149">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="dfbe9-150">Практическое руководство. Добавление и удаление узлов с помощью элемента управления Windows Forms TreeView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-150">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="dfbe9-151">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfbe9-151">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="dfbe9-152">Практическое руководство. Добавление столбцов в Windows Forms элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="dfbe9-152">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
