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
ms.openlocfilehash: 80fd55be9230729cb8336be91c1d8fb4f7f3f080
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364261"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="2687a-102">Пошаговое руководство. Включение перетаскивания для пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="2687a-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="2687a-103">В этом пошаговом руководстве демонстрируется создание настраиваемого пользовательского элемента управления, который может участвовать в переносе данных путем перетаскивания в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2687a-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="2687a-104">В этом пошаговом руководстве вы создадите пользовательский элемент <xref:System.Windows.Controls.UserControl> WPF, представляющий круговую фигуру.</span><span class="sxs-lookup"><span data-stu-id="2687a-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="2687a-105">Вы реализуете в этом элементе управления функциональность, позволяющую переносить данные посредством перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="2687a-106">Например, при перетаскивании из одного элемента управления Circle в другой данные цвета заливки копируются из исходного круга в целевой.</span><span class="sxs-lookup"><span data-stu-id="2687a-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="2687a-107">При перетаскивании элемента управления Circle в объект <xref:System.Windows.Controls.TextBox>строковое представление цвета заливки копируется <xref:System.Windows.Controls.TextBox>в.</span><span class="sxs-lookup"><span data-stu-id="2687a-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="2687a-108">Кроме того, будет создано небольшое приложение, содержащее два элемента управления Panel, <xref:System.Windows.Controls.TextBox> и для тестирования функции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="2687a-109">Вы напишете код, позволяющий панелям обрабатывать перемещенные перетаскиванием данные Circle, в результате чего элементы управления Circle можно будет перемещать или копировать из дочерней коллекции на одной панели в другую.</span><span class="sxs-lookup"><span data-stu-id="2687a-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="2687a-110">В данном пошаговом руководстве рассмотрены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="2687a-111">Создание настраиваемого пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-111">Create a custom user control.</span></span>

- <span data-ttu-id="2687a-112">Включение пользовательского элемента управления в качестве источника перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="2687a-113">Включение пользовательского элемента управления в качестве целевого объекта перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="2687a-114">Включение панели для получения данных, перемещенных перетаскиванием из пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2687a-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2687a-115">Prerequisites</span></span>

<span data-ttu-id="2687a-116">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2687a-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="2687a-117">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="2687a-117">Create the Application Project</span></span>
 <span data-ttu-id="2687a-118">В этом разделе мы создадим инфраструктуру приложений, которая включает главную страницу с двумя панелями и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="2687a-119">Создайте проект приложения WPF на Visual Basic или Visual C# с именем `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="2687a-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="2687a-120">Дополнительные сведения см. в разделе [Пошаговое руководство: Мое первое приложение](../getting-started/walkthrough-my-first-wpf-desktop-application.md)WPF для настольных систем.</span><span class="sxs-lookup"><span data-stu-id="2687a-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="2687a-121">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="2687a-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="2687a-122">Добавьте следующую разметку между открывающим и закрывающим <xref:System.Windows.Controls.Grid> тегами.</span><span class="sxs-lookup"><span data-stu-id="2687a-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="2687a-123">Эта разметка создает пользовательский интерфейс для тестового приложения.</span><span class="sxs-lookup"><span data-stu-id="2687a-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="2687a-124">Добавление нового пользовательского элемента управления в проект</span><span class="sxs-lookup"><span data-stu-id="2687a-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="2687a-125">В этом разделе вы добавите в проект новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="2687a-126">В меню "Проект" выберите пункт **Добавить пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="2687a-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="2687a-127">В диалоговом окне **Добавление нового элемента** измените имя на `Circle.xaml`и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2687a-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="2687a-128">Circle.xaml и его код программной части добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="2687a-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="2687a-129">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="2687a-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="2687a-130">Этот файл будет содержать элементы пользовательского интерфейса пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="2687a-131">Добавьте следующую разметку в корень <xref:System.Windows.Controls.Grid> , чтобы создать простой пользовательский элемент управления с синим кругом в качестве пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2687a-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="2687a-132">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="2687a-133">В C#добавьте следующий код после конструктора без параметров, чтобы создать конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="2687a-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="2687a-134">В Visual Basic добавьте следующий код, чтобы создать конструктор без параметров и конструктор копии.</span><span class="sxs-lookup"><span data-stu-id="2687a-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="2687a-135">Чтобы разрешить копирование пользовательского элемента управления, нужно добавить метод конструктора копии в файле кода программной части.</span><span class="sxs-lookup"><span data-stu-id="2687a-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="2687a-136">В упрощенном пользовательском элементе управления Circle копируются только свойства Fill и размер пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="2687a-137">Добавление пользовательского элемента управления в главное окно</span><span class="sxs-lookup"><span data-stu-id="2687a-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="2687a-138">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="2687a-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="2687a-139">Добавьте следующий код XAML в открывающий <xref:System.Windows.Window> тег, чтобы создать ссылку на пространство имен XML для текущего приложения.</span><span class="sxs-lookup"><span data-stu-id="2687a-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="2687a-140">В первом <xref:System.Windows.Controls.StackPanel>случае добавьте следующий код XAML, чтобы создать два экземпляра пользовательского элемента управления Circle на первой панели.</span><span class="sxs-lookup"><span data-stu-id="2687a-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="2687a-141">Полный код XAML для панели выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2687a-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="2687a-142">Реализация событий источника перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="2687a-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="2687a-143">В этом разделе будет переопределен <xref:System.Windows.UIElement.OnMouseMove%2A> метод и инициирована операция перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="2687a-144">Если перетаскивание начато (нажата кнопка мыши и мышь перемещается), будут упакованы данные, передаваемые в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="2687a-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="2687a-145">В данном случае элемент управления Circle упаковывает три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="2687a-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="2687a-146">Запуск операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="2687a-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="2687a-147">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="2687a-148">Добавьте следующее <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.MouseMove> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="2687a-149">Это <xref:System.Windows.UIElement.OnMouseMove%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-150">Проверяет, нажата ли левая кнопка мыши при перемещении мыши.</span><span class="sxs-lookup"><span data-stu-id="2687a-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="2687a-151">Упаковывает данные круга в <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="2687a-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="2687a-152">В данном случае элемент управления Circle упакует три элемента данных; строковое представление цвета заливки, двойное представление высоты и копию самого себя.</span><span class="sxs-lookup"><span data-stu-id="2687a-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="2687a-153">Вызывает статический <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> метод для инициации операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="2687a-154">В <xref:System.Windows.DragDrop.DoDragDrop%2A> метод передается следующие три параметра:</span><span class="sxs-lookup"><span data-stu-id="2687a-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="2687a-155">`dragSource` — ссылка на этот элемент управления.</span><span class="sxs-lookup"><span data-stu-id="2687a-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="2687a-156">`data`— Объект <xref:System.Windows.DataObject> , созданный в предыдущем коде.</span><span class="sxs-lookup"><span data-stu-id="2687a-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="2687a-157">`allowedEffects`— Разрешенные операции перетаскивания, которые являются <xref:System.Windows.DragDropEffects.Copy> или. <xref:System.Windows.DragDropEffects.Move></span><span class="sxs-lookup"><span data-stu-id="2687a-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="2687a-158">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="2687a-159">Щелкните один из элементов управления Circle и перетащите его над панелями, другим кругом и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="2687a-160">При перетаскивании над <xref:System.Windows.Controls.TextBox>курсор изменяется, чтобы показать перемещение.</span><span class="sxs-lookup"><span data-stu-id="2687a-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="2687a-161">При перетаскивании окружности над <xref:System.Windows.Controls.TextBox>нажмите клавишу **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="2687a-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="2687a-162">Обратите внимание на то, как изменится курсор, обозначая копирование.</span><span class="sxs-lookup"><span data-stu-id="2687a-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="2687a-163">Перетащите окружность на <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="2687a-164">Строковое представление цвета заливки круга добавляется к <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="2687a-165">![Строковое представление цвета заливки элемента управления Circle](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="2687a-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="2687a-166">По умолчанию курсор изменяется во время операции перетаскивания, чтобы указать, какой результат даст перетаскивание данных в ту или иную точку.</span><span class="sxs-lookup"><span data-stu-id="2687a-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="2687a-167">Вы можете настроить отзыв, предоставленный пользователю, обрабатывая <xref:System.Windows.UIElement.GiveFeedback> событие и установив другой курсор.</span><span class="sxs-lookup"><span data-stu-id="2687a-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="2687a-168">Отправьте отзыв пользователю</span><span class="sxs-lookup"><span data-stu-id="2687a-168">Give feedback to the user</span></span>

1. <span data-ttu-id="2687a-169">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="2687a-170">Добавьте следующее <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.GiveFeedback> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="2687a-171">Это <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-172">Проверяет значения, заданные в обработчике <xref:System.Windows.UIElement.DragOver> событий целевого объекта перетаскивания. <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A></span><span class="sxs-lookup"><span data-stu-id="2687a-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="2687a-173">Задает пользовательский курсор на основе <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> значения.</span><span class="sxs-lookup"><span data-stu-id="2687a-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="2687a-174">Курсор предназначен для предоставления визуальной обратной связи пользователю о том, какой результат будет иметь перетаскивание данных.</span><span class="sxs-lookup"><span data-stu-id="2687a-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="2687a-175">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="2687a-176">Перетащите один из элементов управления Circle над панелями, другой окружностью и <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="2687a-177">Обратите внимание, что курсоры теперь являются пользовательскими курсорами, указанными в <xref:System.Windows.UIElement.OnGiveFeedback%2A> переопределении.</span><span class="sxs-lookup"><span data-stu-id="2687a-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="2687a-178">![Перетаскивание с использованием пользовательских курсоров](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="2687a-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="2687a-179">Выберите текст `green` <xref:System.Windows.Controls.TextBox>из.</span><span class="sxs-lookup"><span data-stu-id="2687a-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="2687a-180">Перетащите текст `green` в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="2687a-181">Обратите внимание, что отображаются курсоры по умолчанию: они указывают на результаты операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="2687a-182">Курсор обратной связи всегда задается источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="2687a-183">Реализуйте события назначения перетаскивания в пользовательском элементе управления</span><span class="sxs-lookup"><span data-stu-id="2687a-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="2687a-184">Изучая этот раздел, вы укажете, что пользовательский элемент управления является целевым объектом перетаскивания, переопределите методы, позволяющие пользовательскому элементу управления функционировать в качестве целевого объекта перетаскивания, и обработаете перемещенные в него данные.</span><span class="sxs-lookup"><span data-stu-id="2687a-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="2687a-185">Чтобы включить пользовательский элемент управления в качестве целевого объекта перетаскивания, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2687a-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="2687a-186">Откройте файл Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="2687a-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="2687a-187">В открывающем <xref:System.Windows.Controls.UserControl> теге <xref:System.Windows.UIElement.AllowDrop%2A> добавьте `true`свойство и присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="2687a-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="2687a-188">Метод вызывается, <xref:System.Windows.UIElement.AllowDrop%2A> когда свойство имеет значение `true` , а данные из источника перетаскивания удаляются в пользовательском элементе управления Circle. <xref:System.Windows.UIElement.OnDrop%2A></span><span class="sxs-lookup"><span data-stu-id="2687a-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="2687a-189">В этом методе вы обработаете перемещенные данные и примените их к элементу управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="2687a-190">Обработка вставляемых данных</span><span class="sxs-lookup"><span data-stu-id="2687a-190">To process the dropped data</span></span>

1. <span data-ttu-id="2687a-191">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="2687a-192">Добавьте следующее <xref:System.Windows.UIElement.OnDrop%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.Drop> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="2687a-193">Это <xref:System.Windows.UIElement.OnDrop%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-194"><xref:System.Windows.DataObject.GetDataPresent%2A> Использует метод, чтобы проверить, содержит ли перетаскиваемые данные строковый объект.</span><span class="sxs-lookup"><span data-stu-id="2687a-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="2687a-195"><xref:System.Windows.DataObject.GetData%2A> Использует метод для извлечения строковых данных, если они есть.</span><span class="sxs-lookup"><span data-stu-id="2687a-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="2687a-196">Использует, <xref:System.Windows.Media.BrushConverter> чтобы попытаться преобразовать строку <xref:System.Windows.Media.Brush>в.</span><span class="sxs-lookup"><span data-stu-id="2687a-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="2687a-197">Если преобразование выполнено успешно, применяет кисть к <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> элементу, который предоставляет пользовательский интерфейс элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="2687a-198"><xref:System.Windows.UIElement.Drop> Помечает событие как обработанное.</span><span class="sxs-lookup"><span data-stu-id="2687a-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="2687a-199">Событие сброса необходимо пометить как обработанное, чтобы другие элементы, которые получают это событие, знали, что событие было обработано пользовательским элементом управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="2687a-200">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="2687a-201">Выберите текст `green` в поле <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="2687a-202">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="2687a-203">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="2687a-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="2687a-204">![Преобразование строки в кисть](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="2687a-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="2687a-205">Введите текст `green` в поле <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="2687a-206">Выберите текст `gre` в поле <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="2687a-207">Перетащите его в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="2687a-208">Обратите внимание, что курсор изменяется, чтобы указать, что перенос разрешен, но цвет элемента управления Circle не меняется, потому что `gre` — недопустимый цвет.</span><span class="sxs-lookup"><span data-stu-id="2687a-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="2687a-209">Выполните перетаскивание с зеленого элемента управления Circle на синий.</span><span class="sxs-lookup"><span data-stu-id="2687a-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="2687a-210">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="2687a-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="2687a-211">Обратите внимание, что отображаемый курсор зависит от <xref:System.Windows.Controls.TextBox> того, является ли объект или окружность источником перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2687a-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="2687a-212">Установка свойства в `true` и обработка удаленных данных — это все, что необходимо для того, чтобы элемент можно было использовать в качестве цели перетаскивания. <xref:System.Windows.UIElement.AllowDrop%2A></span><span class="sxs-lookup"><span data-stu-id="2687a-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="2687a-213">Однако, чтобы обеспечить более эффективное взаимодействие с пользователем, необходимо также выполнить обработку <xref:System.Windows.UIElement.DragEnter>событий <xref:System.Windows.UIElement.DragLeave>, и <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="2687a-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="2687a-214">В этих событиях можно выполнять проверки и предоставлять дополнительную обратную связь пользователю до сброса данных.</span><span class="sxs-lookup"><span data-stu-id="2687a-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="2687a-215">При перетаскивании данных над пользовательским элементом управления Circle элемент управления должен уведомить источник перетаскивания, может ли он обработать переносимые данные.</span><span class="sxs-lookup"><span data-stu-id="2687a-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="2687a-216">Если элемент управления не знает, как обрабатывать данные, он должен отклонить перетаскивание.</span><span class="sxs-lookup"><span data-stu-id="2687a-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="2687a-217">Для этого необходимо будет выполнить обработку <xref:System.Windows.UIElement.DragOver> события и <xref:System.Windows.DragEventArgs.Effects%2A> задать свойство.</span><span class="sxs-lookup"><span data-stu-id="2687a-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="2687a-218">Проверка допустимости сброса данных</span><span class="sxs-lookup"><span data-stu-id="2687a-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="2687a-219">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="2687a-220">Добавьте следующее <xref:System.Windows.UIElement.OnDragOver%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragOver> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="2687a-221">Это <xref:System.Windows.UIElement.OnDragOver%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-222">Задает для свойства <xref:System.Windows.DragEventArgs.Effects%2A> значение <xref:System.Windows.DragDropEffects.None>.</span><span class="sxs-lookup"><span data-stu-id="2687a-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="2687a-223">Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> методе, чтобы определить, может ли пользовательский элемент управления Circle обрабатывать перетаскиваемые данные.</span><span class="sxs-lookup"><span data-stu-id="2687a-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="2687a-224">Если пользовательский элемент управления может обработать данные, присваивает <xref:System.Windows.DragEventArgs.Effects%2A> <xref:System.Windows.DragDropEffects.Copy> свойству значение или <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="2687a-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="2687a-225">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="2687a-226">Выберите текст `gre` в поле <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="2687a-227">Перетащите текст в элемент управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="2687a-228">Обратите внимание, что курсор изменяется, чтобы указать, что перетаскивание не разрешено, потому что `gre` не является допустимым цветом.</span><span class="sxs-lookup"><span data-stu-id="2687a-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="2687a-229">Использование предварительного просмотра при перетаскивании повышает удобство работы пользователей.</span><span class="sxs-lookup"><span data-stu-id="2687a-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="2687a-230">Для пользовательского элемента управления Circle будут переопределены <xref:System.Windows.UIElement.OnDragEnter%2A> методы и. <xref:System.Windows.UIElement.OnDragLeave%2A></span><span class="sxs-lookup"><span data-stu-id="2687a-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="2687a-231">При перетаскивании данных над элементом управления текущий фон <xref:System.Windows.Shapes.Shape.Fill%2A> сохраняется в переменной-заполнителе.</span><span class="sxs-lookup"><span data-stu-id="2687a-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="2687a-232">Затем строка преобразуется в кисть и применяется к <xref:System.Windows.Shapes.Ellipse> , которая предоставляет пользовательский интерфейс Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="2687a-233">Если данные перетаскиваются из круга без удаления, исходное <xref:System.Windows.Shapes.Shape.Fill%2A> значение повторно применяется к окружности.</span><span class="sxs-lookup"><span data-stu-id="2687a-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="2687a-234">Предварительный просмотр результатов операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="2687a-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="2687a-235">Откройте файл Circle.xaml.cs или Circle.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="2687a-236">В классе Circle объявите закрытую <xref:System.Windows.Media.Brush> переменную с именем `_previousFill` и инициализируйте `null`ее в.</span><span class="sxs-lookup"><span data-stu-id="2687a-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="2687a-237">Добавьте следующее <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragEnter> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="2687a-238">Это <xref:System.Windows.UIElement.OnDragEnter%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-239"><xref:System.Windows.Shapes.Shape.Fill%2A> Сохраняет свойство<xref:System.Windows.Shapes.Ellipse> объекта в`_previousFill` переменной.</span><span class="sxs-lookup"><span data-stu-id="2687a-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="2687a-240">Выполняет те же проверки, которые выполняются в <xref:System.Windows.UIElement.OnDrop%2A> методе, чтобы определить, можно ли преобразовать данные <xref:System.Windows.Media.Brush>в.</span><span class="sxs-lookup"><span data-stu-id="2687a-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="2687a-241">Если данные преобразуются в допустимый <xref:System.Windows.Media.Brush>объект, применяет <xref:System.Windows.Shapes.Shape.Fill%2A> их к <xref:System.Windows.Shapes.Ellipse>параметру.</span><span class="sxs-lookup"><span data-stu-id="2687a-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="2687a-242">Добавьте следующее <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение, чтобы обеспечить обработку класса <xref:System.Windows.UIElement.DragLeave> для события.</span><span class="sxs-lookup"><span data-stu-id="2687a-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="2687a-243">Это <xref:System.Windows.UIElement.OnDragLeave%2A> переопределение выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-244">Применяет `_previousFill` <xref:System.Windows.Shapes.Shape.Fill%2A> сохраненную в<xref:System.Windows.Shapes.Ellipse> переменной переменную к, которая предоставляет пользовательский интерфейс пользовательского элемента управления Circle. <xref:System.Windows.Media.Brush></span><span class="sxs-lookup"><span data-stu-id="2687a-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="2687a-245">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="2687a-246">Выберите текст `green` в поле <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="2687a-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="2687a-247">Перетащите текст над элементом управления Circle, не сбрасывая его.</span><span class="sxs-lookup"><span data-stu-id="2687a-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="2687a-248">Элемент управления Circle поменяет цвет с синего на зеленый.</span><span class="sxs-lookup"><span data-stu-id="2687a-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="2687a-249">![Предварительный просмотр результатов операции перетаскивания](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="2687a-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="2687a-250">Перетащите текст от элемента управления Circle.</span><span class="sxs-lookup"><span data-stu-id="2687a-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="2687a-251">Элемент управления Circle изменится с зеленого на синий.</span><span class="sxs-lookup"><span data-stu-id="2687a-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="2687a-252">Включение панели для получения потерянных данных</span><span class="sxs-lookup"><span data-stu-id="2687a-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="2687a-253">В этом разделе вы включите панели, в которых размещаются пользовательские элементы управления Circle, чтобы они выступали в качестве целей перетаскивания для перетаскиваемых данных круга.</span><span class="sxs-lookup"><span data-stu-id="2687a-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="2687a-254">Будет реализован код, позволяющий перемещать круг с одной панели на другую или создавать копию элемента управления Circle, удерживая нажатой клавишу **CTRL** при перетаскивании и перетаскивании окружности.</span><span class="sxs-lookup"><span data-stu-id="2687a-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="2687a-255">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="2687a-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="2687a-256">Как показано в следующем коде XAML, в каждом <xref:System.Windows.Controls.StackPanel> элементе управления добавьте обработчики <xref:System.Windows.UIElement.DragOver> для событий и <xref:System.Windows.UIElement.Drop> .</span><span class="sxs-lookup"><span data-stu-id="2687a-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="2687a-257">Назовите обработчик событий, <xref:System.Windows.UIElement.Drop> и`panel_Drop`присвойтеемуимя. `panel_DragOver` <xref:System.Windows.UIElement.DragOver></span><span class="sxs-lookup"><span data-stu-id="2687a-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="2687a-258">Откройте файл MainWindows.xaml.cs или MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="2687a-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="2687a-259">Добавьте следующий код для <xref:System.Windows.UIElement.DragOver> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2687a-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="2687a-260">Этот <xref:System.Windows.UIElement.DragOver> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-261">Проверяет, что перетаскиваемые данные содержат данные "Object", которые были упакованы в <xref:System.Windows.DataObject> с помощью пользовательского элемента управления Circle и передаются в <xref:System.Windows.DragDrop.DoDragDrop%2A>вызов.</span><span class="sxs-lookup"><span data-stu-id="2687a-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="2687a-262">Если имеются данные объекта, проверяет, нажата ли клавиша **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="2687a-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="2687a-263">Если нажата клавиша **CTRL** , присваивает <xref:System.Windows.DragEventArgs.Effects%2A> свойству <xref:System.Windows.DragDropEffects.Copy>значение.</span><span class="sxs-lookup"><span data-stu-id="2687a-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="2687a-264">В противном случае <xref:System.Windows.DragEventArgs.Effects%2A> присвойте <xref:System.Windows.DragDropEffects.Move>свойству значение.</span><span class="sxs-lookup"><span data-stu-id="2687a-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="2687a-265">Добавьте следующий код для <xref:System.Windows.UIElement.Drop> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2687a-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="2687a-266">Этот <xref:System.Windows.UIElement.Drop> обработчик событий выполняет следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2687a-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="2687a-267">Проверяет, <xref:System.Windows.UIElement.Drop> было ли событие уже обработано.</span><span class="sxs-lookup"><span data-stu-id="2687a-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="2687a-268">Например, если окружность отбрасывается на другой круг, который обрабатывает <xref:System.Windows.UIElement.Drop> событие, то панель, содержащая окружность, также не должна обрабатываться.</span><span class="sxs-lookup"><span data-stu-id="2687a-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="2687a-269">Если событие не обрабатывается, проверяет, нажата ли клавиша **CTRL.** <xref:System.Windows.UIElement.Drop></span><span class="sxs-lookup"><span data-stu-id="2687a-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="2687a-270">Если нажата клавиша **CTRL** , когда <xref:System.Windows.UIElement.Drop> происходит, создает копию элемента управления Circle и <xref:System.Windows.Controls.Panel.Children%2A> добавляет ее в коллекцию <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="2687a-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="2687a-271">Если клавиша **CTRL** не нажата, перемещает окружность из <xref:System.Windows.Controls.Panel.Children%2A> коллекции <xref:System.Windows.Controls.Panel.Children%2A> родительской панели в коллекцию панели, в которой она была удалена.</span><span class="sxs-lookup"><span data-stu-id="2687a-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="2687a-272">Задает свойство для <xref:System.Windows.DragDrop.DoDragDrop%2A> уведомления метода о том, была ли выполнена операция перемещения или копирования. <xref:System.Windows.DragEventArgs.Effects%2A></span><span class="sxs-lookup"><span data-stu-id="2687a-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="2687a-273">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2687a-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="2687a-274">Выберите текст `green` <xref:System.Windows.Controls.TextBox>из.</span><span class="sxs-lookup"><span data-stu-id="2687a-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="2687a-275">Перетащите текст над элементом управления Circle и опустите его на элемент.</span><span class="sxs-lookup"><span data-stu-id="2687a-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="2687a-276">Перетащите элемент управления Circle из левой панели в правую панель и опустите его.</span><span class="sxs-lookup"><span data-stu-id="2687a-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="2687a-277">Окружность удаляется из <xref:System.Windows.Controls.Panel.Children%2A> коллекции левой панели и добавляется в коллекцию Children правой панели.</span><span class="sxs-lookup"><span data-stu-id="2687a-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="2687a-278">Перетащите элемент управления Circle с панели на другую панель и поместите его, удерживая нажатой клавишу **CTRL** .</span><span class="sxs-lookup"><span data-stu-id="2687a-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="2687a-279">Окружность копируется, а копия добавляется в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию принимающей панели.</span><span class="sxs-lookup"><span data-stu-id="2687a-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="2687a-280">![Перетаскивание элемента управления Circle с нажатой клавишей CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="2687a-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="2687a-281">См. также</span><span class="sxs-lookup"><span data-stu-id="2687a-281">See also</span></span>

- [<span data-ttu-id="2687a-282">Общие сведения о перетаскивании</span><span class="sxs-lookup"><span data-stu-id="2687a-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
