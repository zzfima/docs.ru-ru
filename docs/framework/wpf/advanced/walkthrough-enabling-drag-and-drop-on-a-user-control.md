---
title: "Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d87872d3009b46878b7b614c1aef728d5b1d511d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="d7a8b-102">Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="d7a8b-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="d7a8b-103">В этом пошаговом руководстве демонстрируется создание настраиваемого пользовательского элемента управления, который может участвовать в переносе данных путем перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7a8b-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="d7a8b-104">В этом пошаговом руководстве вы создадите пользовательский элемент управления WPF <xref:System.Windows.Controls.UserControl> , представляющий круг.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="d7a8b-105">Вы реализуете в этом элементе управления функциональность, позволяющую переносить данные посредством перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="d7a8b-106">Например, при перетаскивании из одного элемента управления Circle в другой данные цвета заливки копируются из исходного круга в целевой.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="d7a8b-107">При перетаскивании элемента управления Circle для <xref:System.Windows.Controls.TextBox>, копируется строковое представление цвета заливки <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d7a8b-108">Также создается небольшое приложение, которое содержит два элемента панели управления и <xref:System.Windows.Controls.TextBox> тестирование функциональности перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="d7a8b-109">Вы напишете код, позволяющий панелям обрабатывать перемещенные перетаскиванием данные Circle, в результате чего элементы управления Circle можно будет перемещать или копировать из дочерней коллекции на одной панели в другую.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="d7a8b-110">В данном пошаговом руководстве рассмотрены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="d7a8b-111">Создание настраиваемого пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="d7a8b-112">Включение пользовательского элемента управления в качестве источника перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="d7a8b-113">Включение пользовательского элемента управления в качестве целевого объекта перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="d7a8b-114">Включение панели для получения данных, перемещенных перетаскиванием из пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d7a8b-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d7a8b-115">Prerequisites</span></span>  
 <span data-ttu-id="d7a8b-116">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="d7a8b-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="d7a8b-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="d7a8b-118">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="d7a8b-118">Creating the Application Project</span></span>  
 <span data-ttu-id="d7a8b-119">В этом разделе вы создадите инфраструктуру приложения, которая включает главную страницу с двумя панелями и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="d7a8b-120">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="d7a8b-120">To create the project</span></span>  
  
1.  <span data-ttu-id="d7a8b-121">Создайте проект приложения WPF на Visual Basic или Visual C# с именем `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="d7a8b-122">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="d7a8b-122">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="d7a8b-123">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="d7a8b-124">Добавьте следующую разметку между открывающим и закрывающим <xref:System.Windows.Controls.Grid> тегов.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="d7a8b-125">Эта разметка создает пользовательский интерфейс для тестового приложения.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="d7a8b-126">Добавление пользовательского элемента управления в проект</span><span class="sxs-lookup"><span data-stu-id="d7a8b-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="d7a8b-127">В этом разделе вы добавите в проект новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="d7a8b-128">Добавление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="d7a8b-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="d7a8b-129">В меню "Проект" выберите пункт **Добавить пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="d7a8b-130">В диалоговом окне "Добавление нового элемента" измените имя на `Circle.xaml` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="d7a8b-131">Circle.xaml и его код программной части добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="d7a8b-132">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="d7a8b-133">Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="d7a8b-134">Добавьте следующую разметку в корневой каталог <xref:System.Windows.Controls.Grid> для создания простой пользовательский элемент управления, который имеет голубой круг в качестве своего пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="d7a8b-135">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="d7a8b-136">В C# добавьте следующий код после конструктора по умолчанию, чтобы создать конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="d7a8b-137">В Visual Basic добавьте следующий код, чтобы создать конструктор по умолчанию и конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="d7a8b-138">Чтобы разрешить копирование пользовательского элемента управления, нужно добавить метод конструктора копии в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="d7a8b-139">В упрощенном пользовательском элементе управления Circle копируются только свойства Fill и размер пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="d7a8b-140">Добавление пользовательского элемента управления в главное окно</span><span class="sxs-lookup"><span data-stu-id="d7a8b-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="d7a8b-141">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="d7a8b-142">Добавьте следующий код XAML в открывающий <xref:System.Windows.Window> тег для создания ссылки на пространство имен XML в текущем приложении.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="d7a8b-143">В первом <xref:System.Windows.Controls.StackPanel>, добавьте следующий код XAML для создания двух экземпляров пользовательский элемент управления Circle первой панели.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="d7a8b-144">Полный код XAML для панели выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="d7a8b-145">Реализация событий источника перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="d7a8b-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="d7a8b-146">В этом разделе будут переопределены <xref:System.Windows.UIElement.OnMouseMove%2A> метод и начать операцию перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="d7a8b-147">Если запущен перетаскивания (кнопка мыши нажата и указатель мыши перемещается) поставляют данные будут передаваться в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="d7a8b-148">В данном случае элемент управления Circle упаковывает три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="d7a8b-149">Запуск операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="d7a8b-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="d7a8b-150">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d7a8b-151">Добавьте следующие <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.MouseMove> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="d7a8b-152">Это <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-153">Проверяет, нажата ли левая кнопка мыши при перемещении мыши.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="d7a8b-154">Упаковывает данные Circle в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="d7a8b-155">В данном случае элемент управления Circle упакует три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="d7a8b-156">Вызывает статический <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> метод для инициализации операции перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="d7a8b-157">Передать следующие три параметра для <xref:System.Windows.DragDrop.DoDragDrop%2A> метод:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="d7a8b-158">`dragSource` — ссылка на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="d7a8b-159">`data`— <xref:System.Windows.DataObject> Создан в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="d7a8b-160">`allowedEffects`Разрешенные операции перетаскивания и вставки, которые являются <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="d7a8b-161">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="d7a8b-162">Выберите один из элементов управления Circle и перетащите его над панелями, другим элементом и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d7a8b-163">При перетаскивании <xref:System.Windows.Controls.TextBox>, курсор изменяется для обозначения перемещения.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="d7a8b-164">При перетаскивании круг <xref:System.Windows.Controls.TextBox>, нажмите клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="d7a8b-165">Обратите внимание на то, как изменится курсор, обозначая копирование.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="d7a8b-166">Перетаскивание круга на <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d7a8b-167">Строковое представление цвета заливки круга добавляется к <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="d7a8b-168">![Строковое представление цвета заливки элемента управления Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="d7a8b-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="d7a8b-169">По умолчанию курсор изменяется во время операции перетаскивания, чтобы указать, какой результат даст перетаскивание данных в ту или иную точку.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="d7a8b-170">Можно настроить получаемую пользователю путем обработки <xref:System.Windows.UIElement.GiveFeedback> событий и задав другой курсор.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="d7a8b-171">Обратная связь с пользователем</span><span class="sxs-lookup"><span data-stu-id="d7a8b-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="d7a8b-172">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d7a8b-173">Добавьте следующие <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.GiveFeedback> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="d7a8b-174">Это <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-175">Проверяет <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значения, заданные в место вставки <xref:System.Windows.UIElement.DragOver> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="d7a8b-176">Задает пользовательский курсор на основе <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="d7a8b-177">Курсор предназначен для предоставления визуальной обратной связи пользователю о том, какой результат будет иметь перетаскивание данных.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="d7a8b-178">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="d7a8b-179">Перетащите одно круга контроль над панелями, другим элементом, и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="d7a8b-180">Обратите внимание, что курсоры теперь пользовательские курсоры, которые указаны в <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределения.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="d7a8b-181">![Перетаскивание с использованием пользовательских курсоров](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="d7a8b-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="d7a8b-182">Выделите текст, `green` из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="d7a8b-183">Перетащите текст `green` в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="d7a8b-184">Обратите внимание, что отображаются курсоры по умолчанию: они указывают на результаты операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="d7a8b-185">Курсор обратной связи всегда задается источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="d7a8b-186">Реализация событий целевого объекта перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="d7a8b-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="d7a8b-187">Изучая этот раздел, вы укажете, что пользовательский элемент управления является целевым объектом перетаскивания, переопределите методы, позволяющие пользовательскому элементу управления функционировать в качестве целевого объекта перетаскивания, и обработаете перемещенные в него данные.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="d7a8b-188">Чтобы включить пользовательский элемент управления в качестве целевого объекта перетаскивания, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="d7a8b-189">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="d7a8b-190">В открывающем <xref:System.Windows.Controls.UserControl> , добавьте <xref:System.Windows.UIElement.AllowDrop%2A> свойство и присвойте ему значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="d7a8b-191"><xref:System.Windows.UIElement.OnDrop%2A> Метод вызывается, когда <xref:System.Windows.UIElement.AllowDrop%2A> свойству `true` и удалении данных из источника перетаскивания в пользовательский элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="d7a8b-192">В этом методе вы обработаете перемещенные данные и примените их к элементу управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="d7a8b-193">Обработка вставляемых данных</span><span class="sxs-lookup"><span data-stu-id="d7a8b-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="d7a8b-194">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d7a8b-195">Добавьте следующие <xref:System.Windows.UIElement.OnDrop%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.Drop> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="d7a8b-196">Это <xref:System.Windows.UIElement.OnDrop%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-197">Использует <xref:System.Windows.DataObject.GetDataPresent%2A> метод для проверки, если перетаскиваемые данные содержат строковый объект.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="d7a8b-198">Использует <xref:System.Windows.DataObject.GetData%2A> метод для извлечения строковых данных, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="d7a8b-199">Использует <xref:System.Windows.Media.BrushConverter> пытается преобразовать строку, <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="d7a8b-200">Если преобразование прошло успешно, применяет кисть к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляет пользовательский Интерфейс элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="d7a8b-201">Метки <xref:System.Windows.UIElement.Drop> событие как обработанное.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="d7a8b-202">Событие сброса необходимо пометить как обработанное, чтобы другие элементы, которые получают это событие, знали, что событие было обработано пользовательским элементом управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="d7a8b-203">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="d7a8b-204">Выделите текст, `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="d7a8b-205">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="d7a8b-206">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="d7a8b-207">![Преобразование строки в кисть](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="d7a8b-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="d7a8b-208">Введите текст `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="d7a8b-209">Выделите текст, `gre` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="d7a8b-210">Перетащите его в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="d7a8b-211">Обратите внимание, что курсор изменяется, чтобы указать, что перенос разрешен, но цвет элемента управления Circle не меняется, потому что `gre` — недопустимый цвет.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="d7a8b-212">Выполните перетаскивание с зеленого элемента управления Circle на синий.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="d7a8b-213">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="d7a8b-214">Обратите внимание, что показано какие курсора зависит от того <xref:System.Windows.Controls.TextBox> или круга является источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="d7a8b-215">Установка <xref:System.Windows.UIElement.AllowDrop%2A> свойства `true` и обработки перетаскиваемых данных — все, что необходимо для включения элемент как конечного расположения сброса.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="d7a8b-216">Однако для повышения удобства работы пользователя, необходимо также обрабатывать <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, и <xref:System.Windows.UIElement.DragOver> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="d7a8b-217">В этих событиях можно выполнять проверки и предоставлять дополнительную обратную связь пользователю до сброса данных.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="d7a8b-218">При перетаскивании данных над пользовательским элементом управления Circle элемент управления должен уведомить источник перетаскивания, может ли он обработать переносимые данные.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="d7a8b-219">Если элемент управления не знает, как обрабатывать данные, он должен отклонить перетаскивание.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="d7a8b-220">Чтобы сделать это, обрабатывающий <xref:System.Windows.UIElement.DragOver> событий и набор <xref:System.Windows.DragEventArgs.Effects%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="d7a8b-221">Проверка допустимости сброса данных</span><span class="sxs-lookup"><span data-stu-id="d7a8b-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="d7a8b-222">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d7a8b-223">Добавьте следующие <xref:System.Windows.UIElement.OnDragOver%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragOver> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="d7a8b-224">Это <xref:System.Windows.UIElement.OnDragOver%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-225">Задает для свойства <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="d7a8b-226">Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, может ли пользовательский элемент управления Circle обработать перетаскиваемые данные.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="d7a8b-227">Если пользовательский элемент управления может обрабатывать данные, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="d7a8b-228">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="d7a8b-229">Выделите текст, `gre` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="d7a8b-230">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="d7a8b-231">Обратите внимание, что курсор изменяется, чтобы указать, что перетаскивание не разрешено, потому что `gre` не является допустимым цветом.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="d7a8b-232">Использование предварительного просмотра при перетаскивании повышает удобство работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="d7a8b-233">Пользовательский элемент управления Circle будут переопределены <xref:System.Windows.UIElement.OnDragEnter%2A> и <xref:System.Windows.UIElement.OnDragLeave%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="d7a8b-234">При перетаскивании данных над элементом управления, текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной заполнителя.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="d7a8b-235">Затем строка преобразуется в кисть и применены к <xref:System.Windows.Shapes.Ellipse> , предоставляющий круга пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="d7a8b-236">Если перетаскиваемые данные вне круга без отпускания исходного <xref:System.Windows.Shapes.Shape.Fill%2A> повторно применяется значение круга.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="d7a8b-237">Предварительный просмотр результатов операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="d7a8b-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="d7a8b-238">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="d7a8b-239">В классе Circle объявить закрытый <xref:System.Windows.Media.Brush> переменную с именем `_previousFill` и инициализируйте его, чтобы `null`.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="d7a8b-240">Добавьте следующие <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragEnter> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="d7a8b-241">Это <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-242">Сохраняет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство <xref:System.Windows.Shapes.Ellipse> в `_previousFill` переменной.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="d7a8b-243">Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, будут ли данные могут преобразовываться в <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="d7a8b-244">Если данные преобразуются в допустимый <xref:System.Windows.Media.Brush>, применяется к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="d7a8b-245">Добавьте следующие <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение обеспечивают обработку класса для <xref:System.Windows.UIElement.DragLeave> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="d7a8b-246">Это <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-247">Применяет <xref:System.Windows.Media.Brush> сохраняется в `_previousFill` переменной <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляет пользовательский Интерфейс пользовательского элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="d7a8b-248">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="d7a8b-249">Выделите текст, `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="d7a8b-250">Перетащите текст над элементом управления Circle, не сбрасывая его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="d7a8b-251">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="d7a8b-252">![Предварительный просмотр результатов операции перетаскивания](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="d7a8b-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="d7a8b-253">Перетащите текст от элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="d7a8b-254">Элемент управления Circle изменится с зеленого на синий.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="d7a8b-255">Настройка панели для получения перемещенных данных</span><span class="sxs-lookup"><span data-stu-id="d7a8b-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="d7a8b-256">В этом разделе вы включите использование панелей, на которых размещены пользовательские элементы управления Circle, в качестве целевых объектов перетаскивания для перемещенных данных Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="d7a8b-257">Будет реализован код, который позволяет переместить элемент Circle с одной панели на другую или копировать этот элемент, удерживая нажатой клавишу CTRL при перетаскивании элемента Circle.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="d7a8b-258">Включение панели в качестве целевого объекта перетаскивания</span><span class="sxs-lookup"><span data-stu-id="d7a8b-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="d7a8b-259">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="d7a8b-260">Как показано в следующем XAML, в каждом из <xref:System.Windows.Controls.StackPanel> элементы управления, добавьте обработчики для <xref:System.Windows.UIElement.DragOver> и <xref:System.Windows.UIElement.Drop> события.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="d7a8b-261">Имя <xref:System.Windows.UIElement.DragOver> обработчик событий `panel_DragOver`и назовите <xref:System.Windows.UIElement.Drop> обработчик событий `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="d7a8b-262">Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="d7a8b-263">Добавьте следующий код для <xref:System.Windows.UIElement.DragOver> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="d7a8b-264">Это <xref:System.Windows.UIElement.DragOver> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-265">Проверяет переносимых данных, который содержит данные «Объект», которая была упакована в <xref:System.Windows.DataObject> , пользовательский элемент управления Circle и передается в вызове <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="d7a8b-266">Если данные типа "Объект" присутствуют, обработчик проверяет нажата ли клавиша CTRL.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="d7a8b-267">Если нажата клавиша CTRL, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="d7a8b-268">В противном случае <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="d7a8b-269">Добавьте следующий код для <xref:System.Windows.UIElement.Drop> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="d7a8b-270">Это <xref:System.Windows.UIElement.Drop> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d7a8b-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="d7a8b-271">Проверяет, является ли <xref:System.Windows.UIElement.Drop> уже обработано событие.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="d7a8b-272">Например, при удалении круг на другом Circle которой дескрипторы <xref:System.Windows.UIElement.Drop> событий, нужно панели, содержащей круг обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="d7a8b-273">Если <xref:System.Windows.UIElement.Drop> событие не обрабатывается, проверяет ли нажата клавиша CTRL.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="d7a8b-274">Если нажата клавиша CTRL при <xref:System.Windows.UIElement.Drop> происходит делает копию круга, управления и добавьте его к <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="d7a8b-275">Если не нажата клавиша CTRL, перемещает элемент управления Circle из <xref:System.Windows.Controls.Panel.Children%2A> коллекцию его родительской панели <xref:System.Windows.Controls.Panel.Children%2A> коллекцию на панели, который он был удален.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="d7a8b-276">Наборы <xref:System.Windows.DragEventArgs.Effects%2A> свойство известить <xref:System.Windows.DragDrop.DoDragDrop%2A> метод выполнение операции перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="d7a8b-277">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="d7a8b-278">Выделите текст, `green` из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="d7a8b-279">Перетащите текст над элементом управления Circle и опустите его на элемент.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="d7a8b-280">Перетащите элемент управления Circle из левой панели в правую панель и опустите его.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="d7a8b-281">Круг удаляется из <xref:System.Windows.Controls.Panel.Children%2A> коллекцию левой панели и добавляется в коллекцию Children правой панели.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="d7a8b-282">Перетащите элемент управления Circle с панели, на которой он находится, на другую панель и опустите, не отпуская клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="d7a8b-283">Круг копируется и добавляется копия <xref:System.Windows.Controls.Panel.Children%2A> коллекции, принимающей панели.</span><span class="sxs-lookup"><span data-stu-id="d7a8b-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="d7a8b-284">![Перетаскивание элемента управления Circle с нажатой клавишей CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="d7a8b-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a8b-285">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a8b-285">See Also</span></span>  
 [<span data-ttu-id="d7a8b-286">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="d7a8b-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
