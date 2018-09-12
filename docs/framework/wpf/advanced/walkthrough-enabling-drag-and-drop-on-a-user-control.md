---
title: Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: e151eb7f428fecb330970210fd7addb1603a211f
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44514700"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="4526d-102">Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="4526d-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="4526d-103">В этом пошаговом руководстве демонстрируется создание настраиваемого пользовательского элемента управления, который может участвовать в переносе данных путем перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4526d-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="4526d-104">В этом пошаговом руководстве вы создадите настраиваемый элемент управления WPF <xref:System.Windows.Controls.UserControl> , представляющий круг.</span><span class="sxs-lookup"><span data-stu-id="4526d-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="4526d-105">Вы реализуете в этом элементе управления функциональность, позволяющую переносить данные посредством перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="4526d-106">Например, при перетаскивании из одного элемента управления Circle в другой данные цвета заливки копируются из исходного круга в целевой.</span><span class="sxs-lookup"><span data-stu-id="4526d-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="4526d-107">Если перетащить элемент управления Circle на <xref:System.Windows.Controls.TextBox>, строковое представление цвета заливки копируется в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4526d-108">Вы также создадите небольшое приложение, которое содержит два элемента управления панели и <xref:System.Windows.Controls.TextBox> для тестирования функциональности перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="4526d-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="4526d-109">Вы напишете код, позволяющий панелям обрабатывать перемещенные перетаскиванием данные Circle, в результате чего элементы управления Circle можно будет перемещать или копировать из дочерней коллекции на одной панели в другую.</span><span class="sxs-lookup"><span data-stu-id="4526d-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="4526d-110">В данном пошаговом руководстве рассмотрены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="4526d-111">Создание настраиваемого пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="4526d-112">Включение пользовательского элемента управления в качестве источника перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="4526d-113">Включение пользовательского элемента управления в качестве целевого объекта перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="4526d-114">Включение панели для получения данных, перемещенных перетаскиванием из пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4526d-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4526d-115">Prerequisites</span></span>  
 <span data-ttu-id="4526d-116">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="4526d-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="4526d-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="4526d-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="4526d-118">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="4526d-118">Creating the Application Project</span></span>  
 <span data-ttu-id="4526d-119">В этом разделе вы создадите инфраструктуру приложения, которая включает главную страницу с двумя панелями и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="4526d-120">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4526d-120">To create the project</span></span>  
  
1.  <span data-ttu-id="4526d-121">Создайте проект приложения WPF на Visual Basic или Visual C# с именем `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="4526d-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="4526d-122">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="4526d-122">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="4526d-123">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4526d-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="4526d-124">Добавьте следующую разметку между открывающим и закрывающим <xref:System.Windows.Controls.Grid> теги.</span><span class="sxs-lookup"><span data-stu-id="4526d-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="4526d-125">Эта разметка создает пользовательский интерфейс для тестового приложения.</span><span class="sxs-lookup"><span data-stu-id="4526d-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="4526d-126">Добавление пользовательского элемента управления в проект</span><span class="sxs-lookup"><span data-stu-id="4526d-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="4526d-127">В этом разделе вы добавите в проект новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="4526d-128">Добавление пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="4526d-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="4526d-129">В меню "Проект" выберите пункт **Добавить пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="4526d-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="4526d-130">В диалоговом окне "Добавление нового элемента" измените имя на `Circle.xaml` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4526d-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="4526d-131">Circle.xaml и его код программной части добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="4526d-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="4526d-132">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="4526d-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="4526d-133">Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="4526d-134">Добавьте следующую разметку в корневой каталог <xref:System.Windows.Controls.Grid> создать простой пользовательский элемент управления, который представлен синим кругом, пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4526d-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="4526d-135">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="4526d-136">В C# добавьте следующий код после конструктора по умолчанию, чтобы создать конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="4526d-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="4526d-137">В Visual Basic добавьте следующий код, чтобы создать конструктор по умолчанию и конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="4526d-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="4526d-138">Чтобы разрешить копирование пользовательского элемента управления, нужно добавить метод конструктора копии в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="4526d-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="4526d-139">В упрощенном пользовательском элементе управления Circle копируются только свойства Fill и размер пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="4526d-140">Добавление пользовательского элемента управления в главное окно</span><span class="sxs-lookup"><span data-stu-id="4526d-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="4526d-141">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4526d-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="4526d-142">Добавьте следующий XAML в открывающий <xref:System.Windows.Window> тег, чтобы создать ссылку на пространство имен XML для текущего приложения.</span><span class="sxs-lookup"><span data-stu-id="4526d-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="4526d-143">В первом <xref:System.Windows.Controls.StackPanel>, добавьте следующий XAML для создания двух экземпляров пользовательского элемента управления Circle на первой панели.</span><span class="sxs-lookup"><span data-stu-id="4526d-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="4526d-144">Полный код XAML для панели выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4526d-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="4526d-145">Реализация событий источника перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="4526d-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="4526d-146">В этом разделе будут переопределены <xref:System.Windows.UIElement.OnMouseMove%2A> метод и инициирует операцию перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="4526d-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="4526d-147">Если перетаскивание начато (нажата кнопка мыши и перемещение мыши), позволяющий преобразовывать данные будут передаваться в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="4526d-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="4526d-148">В данном случае элемент управления Circle упаковывает три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="4526d-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="4526d-149">Запуск операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="4526d-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="4526d-150">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="4526d-151">Добавьте следующий <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.MouseMove> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="4526d-152">Это <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-153">Проверяет, нажата ли левая кнопка мыши при перемещении мыши.</span><span class="sxs-lookup"><span data-stu-id="4526d-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="4526d-154">Упаковывает данные Circle в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="4526d-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="4526d-155">В данном случае элемент управления Circle упакует три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="4526d-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="4526d-156">Вызывает статический <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> метода для инициации операции перетаскивания и вставки.</span><span class="sxs-lookup"><span data-stu-id="4526d-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="4526d-157">Передайте следующие три параметра для <xref:System.Windows.DragDrop.DoDragDrop%2A> метод:</span><span class="sxs-lookup"><span data-stu-id="4526d-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="4526d-158">`dragSource` — ссылка на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4526d-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="4526d-159">`data` — <xref:System.Windows.DataObject> Созданный в предыдущем коде.</span><span class="sxs-lookup"><span data-stu-id="4526d-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="4526d-160">`allowedEffects` Разрешенные операции перетаскивания и вставки, которые являются <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4526d-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="4526d-161">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="4526d-162">Выберите один из элементов управления Circle и перетащите его над панелями, другим элементом Circle и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4526d-163">При перетаскивании над <xref:System.Windows.Controls.TextBox>, курсор изменяется, обозначая перемещение.</span><span class="sxs-lookup"><span data-stu-id="4526d-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="4526d-164">При перетаскивании элемента управления Circle над <xref:System.Windows.Controls.TextBox>, нажмите клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="4526d-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="4526d-165">Обратите внимание на то, как изменится курсор, обозначая копирование.</span><span class="sxs-lookup"><span data-stu-id="4526d-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="4526d-166">Перетащите элемент управления Circle на <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4526d-167">Строковое представление цвета заливки элемента управления Circle добавляется к <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="4526d-168">![Строковое представление цвета заливки элемента управления Circle](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="4526d-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="4526d-169">По умолчанию курсор изменяется во время операции перетаскивания, чтобы указать, какой результат даст перетаскивание данных в ту или иную точку.</span><span class="sxs-lookup"><span data-stu-id="4526d-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="4526d-170">Можно настроить получаемую пользователем путем обработки <xref:System.Windows.UIElement.GiveFeedback> событий и настройки другого курсора.</span><span class="sxs-lookup"><span data-stu-id="4526d-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="4526d-171">Обратная связь с пользователем</span><span class="sxs-lookup"><span data-stu-id="4526d-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="4526d-172">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="4526d-173">Добавьте следующий <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.GiveFeedback> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="4526d-174">Это <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-175">Проверяет <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значения, заданные в цели перетаскивания <xref:System.Windows.UIElement.DragOver> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="4526d-176">Задает пользовательский курсор на основе <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="4526d-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="4526d-177">Курсор предназначен для предоставления визуальной обратной связи пользователю о том, какой результат будет иметь перетаскивание данных.</span><span class="sxs-lookup"><span data-stu-id="4526d-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="4526d-178">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="4526d-179">Перетащите один из круга управляет над панелями, другим элементом Circle, и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="4526d-180">Обратите внимание, что курсоры созданы пользовательские курсоры, которые указаны в <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределить.</span><span class="sxs-lookup"><span data-stu-id="4526d-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="4526d-181">![Перетаскивание с использованием пользовательских курсоров](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="4526d-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="4526d-182">Выделите текст `green` из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="4526d-183">Перетащите текст `green` в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="4526d-184">Обратите внимание, что отображаются курсоры по умолчанию: они указывают на результаты операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="4526d-185">Курсор обратной связи всегда задается источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="4526d-186">Реализация событий целевого объекта перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="4526d-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="4526d-187">Изучая этот раздел, вы укажете, что пользовательский элемент управления является целевым объектом перетаскивания, переопределите методы, позволяющие пользовательскому элементу управления функционировать в качестве целевого объекта перетаскивания, и обработаете перемещенные в него данные.</span><span class="sxs-lookup"><span data-stu-id="4526d-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="4526d-188">Чтобы включить пользовательский элемент управления в качестве целевого объекта перетаскивания, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4526d-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="4526d-189">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="4526d-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="4526d-190">В открывающем <xref:System.Windows.Controls.UserControl> , добавьте <xref:System.Windows.UIElement.AllowDrop%2A> свойство и присвойте ему значение `true`.</span><span class="sxs-lookup"><span data-stu-id="4526d-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="4526d-191"><xref:System.Windows.UIElement.OnDrop%2A> Метод вызывается, когда <xref:System.Windows.UIElement.AllowDrop%2A> свойству `true` и удалении данных из источника перетаскивания в пользовательский элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="4526d-192">В этом методе вы обработаете перемещенные данные и примените их к элементу управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="4526d-193">Обработка вставляемых данных</span><span class="sxs-lookup"><span data-stu-id="4526d-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="4526d-194">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="4526d-195">Добавьте следующий <xref:System.Windows.UIElement.OnDrop%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.Drop> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="4526d-196">Это <xref:System.Windows.UIElement.OnDrop%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-197">Использует <xref:System.Windows.DataObject.GetDataPresent%2A> метод, чтобы проверить наличие перемещенные данные строковый объект.</span><span class="sxs-lookup"><span data-stu-id="4526d-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="4526d-198">Использует <xref:System.Windows.DataObject.GetData%2A> метод для извлечения строковых данных в том случае, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="4526d-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="4526d-199">Использует <xref:System.Windows.Media.BrushConverter> для строки, преобразованные в <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="4526d-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="4526d-200">Если преобразование прошло успешно, применяет кисть к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляет пользовательский Интерфейс элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="4526d-201">Метки <xref:System.Windows.UIElement.Drop> событие как обработанное.</span><span class="sxs-lookup"><span data-stu-id="4526d-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="4526d-202">Событие сброса необходимо пометить как обработанное, чтобы другие элементы, которые получают это событие, знали, что событие было обработано пользовательским элементом управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="4526d-203">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="4526d-204">Выделите текст `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="4526d-205">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="4526d-206">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="4526d-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="4526d-207">![Преобразование строки в кисть](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="4526d-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="4526d-208">Введите текст `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="4526d-209">Выделите текст `gre` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="4526d-210">Перетащите его в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="4526d-211">Обратите внимание, что курсор изменяется, чтобы указать, что перенос разрешен, но цвет элемента управления Circle не меняется, потому что `gre` — недопустимый цвет.</span><span class="sxs-lookup"><span data-stu-id="4526d-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="4526d-212">Выполните перетаскивание с зеленого элемента управления Circle на синий.</span><span class="sxs-lookup"><span data-stu-id="4526d-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="4526d-213">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="4526d-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="4526d-214">Обратите внимание, что отображается курсор, который зависит от того <xref:System.Windows.Controls.TextBox> или элемент управления Circle является источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="4526d-215">Установка <xref:System.Windows.UIElement.AllowDrop%2A> свойства `true` и обработка перенесенных данных — все, что требуется для включения элемента в качестве целевого объекта перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="4526d-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="4526d-216">Тем не менее, для повышения удобства работы пользователя, необходимо также обрабатывать <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, и <xref:System.Windows.UIElement.DragOver> события.</span><span class="sxs-lookup"><span data-stu-id="4526d-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="4526d-217">В этих событиях можно выполнять проверки и предоставлять дополнительную обратную связь пользователю до сброса данных.</span><span class="sxs-lookup"><span data-stu-id="4526d-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="4526d-218">При перетаскивании данных над пользовательским элементом управления Circle элемент управления должен уведомить источник перетаскивания, может ли он обработать переносимые данные.</span><span class="sxs-lookup"><span data-stu-id="4526d-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="4526d-219">Если элемент управления не знает, как обрабатывать данные, он должен отклонить перетаскивание.</span><span class="sxs-lookup"><span data-stu-id="4526d-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="4526d-220">Чтобы сделать это, будет обрабатывать <xref:System.Windows.UIElement.DragOver> событий и набор <xref:System.Windows.DragEventArgs.Effects%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4526d-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="4526d-221">Проверка допустимости сброса данных</span><span class="sxs-lookup"><span data-stu-id="4526d-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="4526d-222">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="4526d-223">Добавьте следующий <xref:System.Windows.UIElement.OnDragOver%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.DragOver> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="4526d-224">Это <xref:System.Windows.UIElement.OnDragOver%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-225">Задает для свойства <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="4526d-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="4526d-226">Выполняет те же проверки, выполняемые в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, может ли пользовательский элемент управления Circle обработать перенесенные данные.</span><span class="sxs-lookup"><span data-stu-id="4526d-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="4526d-227">Если пользовательский элемент управления может обработать данные, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy> или <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4526d-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="4526d-228">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="4526d-229">Выделите текст `gre` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="4526d-230">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="4526d-231">Обратите внимание, что курсор изменяется, чтобы указать, что перетаскивание не разрешено, потому что `gre` не является допустимым цветом.</span><span class="sxs-lookup"><span data-stu-id="4526d-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="4526d-232">Использование предварительного просмотра при перетаскивании повышает удобство работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="4526d-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="4526d-233">Для пользовательского элемента управления Circle переопределяются <xref:System.Windows.UIElement.OnDragEnter%2A> и <xref:System.Windows.UIElement.OnDragLeave%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="4526d-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="4526d-234">Когда данные перетаскиваются над элементом управления, текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной-заполнителе.</span><span class="sxs-lookup"><span data-stu-id="4526d-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="4526d-235">Затем строка преобразуется в кисть и применяется к <xref:System.Windows.Shapes.Ellipse> , предоставляющий окружности пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4526d-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="4526d-236">Если данные перетаскиваются за элемент управления Circle без сброса, исходное <xref:System.Windows.Shapes.Shape.Fill%2A> значение повторно применить к элементу управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="4526d-237">Предварительный просмотр результатов операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="4526d-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="4526d-238">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="4526d-239">В классе Circle объявите закрытую <xref:System.Windows.Media.Brush> переменную с именем `_previousFill` и инициализируйте его, чтобы `null`.</span><span class="sxs-lookup"><span data-stu-id="4526d-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="4526d-240">Добавьте следующий <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.DragEnter> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="4526d-241">Это <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-242">Сохраняет <xref:System.Windows.Shapes.Shape.Fill%2A> свойство <xref:System.Windows.Shapes.Ellipse> в `_previousFill` переменной.</span><span class="sxs-lookup"><span data-stu-id="4526d-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="4526d-243">Выполняет те же проверки, выполняемые в <xref:System.Windows.UIElement.OnDrop%2A> метод, чтобы определить, может быть преобразован в данных <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="4526d-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="4526d-244">Если данные преобразуются в допустимый <xref:System.Windows.Media.Brush>, применяемое к <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="4526d-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="4526d-245">Добавьте следующий <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение, чтобы обеспечить обработку класса для <xref:System.Windows.UIElement.DragLeave> событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="4526d-246">Это <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-247">Применяет <xref:System.Windows.Media.Brush> сохранен в `_previousFill` переменной <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Ellipse> , предоставляющий пользовательского интерфейса пользовательского элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="4526d-248">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="4526d-249">Выделите текст `green` в <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="4526d-250">Перетащите текст над элементом управления Circle, не сбрасывая его.</span><span class="sxs-lookup"><span data-stu-id="4526d-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="4526d-251">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="4526d-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="4526d-252">![Предварительный просмотр результатов операции перетаскивания](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="4526d-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="4526d-253">Перетащите текст от элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="4526d-254">Элемент управления Circle изменится с зеленого на синий.</span><span class="sxs-lookup"><span data-stu-id="4526d-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="4526d-255">Настройка панели для получения перемещенных данных</span><span class="sxs-lookup"><span data-stu-id="4526d-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="4526d-256">В этом разделе вы включите использование панелей, на которых размещены пользовательские элементы управления Circle, в качестве целевых объектов перетаскивания для перемещенных данных Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="4526d-257">Будет реализован код, который позволяет переместить элемент Circle с одной панели на другую или копировать этот элемент, удерживая нажатой клавишу CTRL при перетаскивании элемента Circle.</span><span class="sxs-lookup"><span data-stu-id="4526d-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="4526d-258">Включение панели в качестве целевого объекта перетаскивания</span><span class="sxs-lookup"><span data-stu-id="4526d-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="4526d-259">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4526d-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="4526d-260">Как показано в следующем XAML, в каждом из <xref:System.Windows.Controls.StackPanel> элементы управления, добавьте обработчики для <xref:System.Windows.UIElement.DragOver> и <xref:System.Windows.UIElement.Drop> события.</span><span class="sxs-lookup"><span data-stu-id="4526d-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="4526d-261">Имя <xref:System.Windows.UIElement.DragOver> обработчик событий `panel_DragOver`и назовите <xref:System.Windows.UIElement.Drop> обработчик событий `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="4526d-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="4526d-262">Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="4526d-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="4526d-263">Добавьте следующий код для <xref:System.Windows.UIElement.DragOver> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="4526d-264">Это <xref:System.Windows.UIElement.DragOver> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-265">Проверяет, что перетаскиваемые данные с данными «Объект», было упаковано в <xref:System.Windows.DataObject> с пользовательским элементом управления Circle и переданы в вызове <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="4526d-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="4526d-266">Если данные типа "Объект" присутствуют, обработчик проверяет нажата ли клавиша CTRL.</span><span class="sxs-lookup"><span data-stu-id="4526d-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="4526d-267">Если клавиша CTRL нажата, задает <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="4526d-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="4526d-268">В противном случае значение <xref:System.Windows.DragEventArgs.Effects%2A> свойства <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="4526d-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="4526d-269">Добавьте следующий код для <xref:System.Windows.UIElement.Drop> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="4526d-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="4526d-270">Это <xref:System.Windows.UIElement.Drop> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4526d-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="4526d-271">Проверяет ли <xref:System.Windows.UIElement.Drop> уже было обработано событие.</span><span class="sxs-lookup"><span data-stu-id="4526d-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="4526d-272">Например, если элемент управления Circle перетаскивается на другом круг которого дескрипторы <xref:System.Windows.UIElement.Drop> событий, требуется панель, содержащую круг его.</span><span class="sxs-lookup"><span data-stu-id="4526d-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="4526d-273">Если <xref:System.Windows.UIElement.Drop> событие не обработано, проверяет ли клавиша CTRL нажата.</span><span class="sxs-lookup"><span data-stu-id="4526d-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="4526d-274">Если клавиша CTRL нажата <xref:System.Windows.UIElement.Drop> происходит, создает копию круга управления и добавьте его в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="4526d-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="4526d-275">Если клавиша CTRL не нажата, перемещает элемент управления Circle из <xref:System.Windows.Controls.Panel.Children%2A> коллекцию его родительской панели <xref:System.Windows.Controls.Panel.Children%2A> коллекцию на панели, который был сброшен.</span><span class="sxs-lookup"><span data-stu-id="4526d-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="4526d-276">Наборы <xref:System.Windows.DragEventArgs.Effects%2A> свойства для уведомления <xref:System.Windows.DragDrop.DoDragDrop%2A> метод ли была выполнена операция перемещения или копирования.</span><span class="sxs-lookup"><span data-stu-id="4526d-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="4526d-277">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4526d-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="4526d-278">Выделите текст `green` из <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="4526d-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="4526d-279">Перетащите текст над элементом управления Circle и опустите его на элемент.</span><span class="sxs-lookup"><span data-stu-id="4526d-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="4526d-280">Перетащите элемент управления Circle из левой панели в правую панель и опустите его.</span><span class="sxs-lookup"><span data-stu-id="4526d-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="4526d-281">Элемент управления Circle удаляется из <xref:System.Windows.Controls.Panel.Children%2A> коллекции левой панели и добавляется в коллекцию дочерних элементов на правой панели.</span><span class="sxs-lookup"><span data-stu-id="4526d-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="4526d-282">Перетащите элемент управления Circle с панели, на которой он находится, на другую панель и опустите, не отпуская клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="4526d-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="4526d-283">Элемент управления Circle копируется, и копия добавляется <xref:System.Windows.Controls.Panel.Children%2A> коллекцию принимающей панели.</span><span class="sxs-lookup"><span data-stu-id="4526d-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="4526d-284">![Перетаскивание элемента управления Circle с нажатой клавишей CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="4526d-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4526d-285">См. также</span><span class="sxs-lookup"><span data-stu-id="4526d-285">See Also</span></span>  
 [<span data-ttu-id="4526d-286">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="4526d-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
