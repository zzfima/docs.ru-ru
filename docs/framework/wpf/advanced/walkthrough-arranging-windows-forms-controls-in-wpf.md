---
title: Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 3a94ef65be99b01a9511f37872cbcacd6ec12264
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179438"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="6eb73-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="6eb73-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="6eb73-103">В этом пошаговом руководстве показано, как использовать функции макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для упорядочения элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в гибридном приложении.</span><span class="sxs-lookup"><span data-stu-id="6eb73-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="6eb73-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="6eb73-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6eb73-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="6eb73-105">Creating the project.</span></span>
- <span data-ttu-id="6eb73-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6eb73-106">Using default layout settings.</span></span>
- <span data-ttu-id="6eb73-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="6eb73-107">Sizing to content.</span></span>
- <span data-ttu-id="6eb73-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="6eb73-108">Using absolute positioning.</span></span>
- <span data-ttu-id="6eb73-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="6eb73-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="6eb73-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="6eb73-110">Setting layout properties.</span></span>
- <span data-ttu-id="6eb73-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="6eb73-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="6eb73-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="6eb73-112">Docking.</span></span>
- <span data-ttu-id="6eb73-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="6eb73-113">Setting visibility.</span></span>
- <span data-ttu-id="6eb73-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6eb73-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="6eb73-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="6eb73-115">Scaling.</span></span>
- <span data-ttu-id="6eb73-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="6eb73-116">Rotating.</span></span>
- <span data-ttu-id="6eb73-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="6eb73-117">Setting padding and margins.</span></span>
- <span data-ttu-id="6eb73-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="6eb73-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="6eb73-119">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Размещение элементов управления Windows Forms в WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="6eb73-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="6eb73-120">По завершении вы получите представление о функциях макета [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в @no__t приложениях на основе -1.</span><span class="sxs-lookup"><span data-stu-id="6eb73-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6eb73-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6eb73-121">Prerequisites</span></span>

<span data-ttu-id="6eb73-122">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6eb73-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="6eb73-123">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="6eb73-123">Creating the Project</span></span>

<span data-ttu-id="6eb73-124">Чтобы создать и настроить проект, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-125">Создайте проект приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="6eb73-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="6eb73-126">В обозреватель решений добавьте ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="6eb73-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="6eb73-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6eb73-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="6eb73-128">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="6eb73-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="6eb73-129">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="6eb73-129">System.Drawing</span></span>

3. <span data-ttu-id="6eb73-130">Дважды щелкните файл *MainWindow. XAML* , чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="6eb73-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="6eb73-131">В элемент <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="6eb73-132">В элементе <xref:System.Windows.Controls.Grid> задайте для свойства <xref:System.Windows.Controls.Grid.ShowGridLines%2A> значение `true` и определите пять строк и три столбца.</span><span class="sxs-lookup"><span data-stu-id="6eb73-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="6eb73-133">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="6eb73-133">Using Default Layout Settings</span></span>

<span data-ttu-id="6eb73-134">По умолчанию элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрабатывает макет для размещенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="6eb73-135">Чтобы использовать параметры макета по умолчанию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-136">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="6eb73-137">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-138">Элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> отображается в <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6eb73-139">Размер размещаемого элемента управления зависит от его содержимого, а размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяется в соответствии с размещаемым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6eb73-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="6eb73-140">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="6eb73-140">Sizing to Content</span></span>

<span data-ttu-id="6eb73-141">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> гарантирует, что размещаемый элемент управления будет иметь размер, чтобы правильно отобразить его содержимое.</span><span class="sxs-lookup"><span data-stu-id="6eb73-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="6eb73-142">Чтобы задать размер содержимого, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-143">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="6eb73-144">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-145">Два новых элемента управления "Кнопка" имеют размер, чтобы правильно отображать более длинную текстовую строку и больший размер шрифта, а размеры элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяются в соответствии с размещаемыми элементами управления.</span><span class="sxs-lookup"><span data-stu-id="6eb73-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="6eb73-146">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="6eb73-146">Using Absolute Positioning</span></span>

<span data-ttu-id="6eb73-147">Можно использовать абсолютное позиционирование для размещения элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> в любом месте пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6eb73-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="6eb73-148">Чтобы использовать абсолютное позиционирование, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-149">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="6eb73-150">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-151">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> размещается на 20 пикселях с верхней стороны ячейки сетки и на 20 пикселях слева.</span><span class="sxs-lookup"><span data-stu-id="6eb73-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="6eb73-152">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="6eb73-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="6eb73-153">Можно указать размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> с помощью свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="6eb73-154">Чтобы указать размер явным образом, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-155">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="6eb73-156">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-157">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> задается размером 50 пикселей в ширину на 70 пикселей высотой, что меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6eb73-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="6eb73-158">Содержимое элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="6eb73-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="6eb73-159">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="6eb73-159">Setting Layout Properties</span></span>

<span data-ttu-id="6eb73-160">Всегда устанавливайте свойства, связанные с макетом, в размещенном элементе управления с помощью свойств элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eb73-161">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="6eb73-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="6eb73-162">Установка свойств, связанных с макетом, для размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="6eb73-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="6eb73-163">Чтобы увидеть влияние установки свойств на размещенном элементе управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-164">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="6eb73-165">В **Обозреватель решений**дважды щелкните файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS* , чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="6eb73-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="6eb73-166">Скопируйте следующий код в определение класса `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="6eb73-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="6eb73-167">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="6eb73-168">Нажмите кнопку " **щелкните мне** ".</span><span class="sxs-lookup"><span data-stu-id="6eb73-168">Click the **Click me** button.</span></span> <span data-ttu-id="6eb73-169">Обработчик событий `button1_Click` задает свойства <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> для размещаемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6eb73-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="6eb73-170">Это приводит к перемещению размещенного элемента управления в элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eb73-171">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="6eb73-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="6eb73-172">Вместо этого размещаемый элемент управления всегда должен заполнить элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="6eb73-173">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="6eb73-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="6eb73-174">Видимые элементы <xref:System.Windows.Forms.Integration.WindowsFormsHost> всегда рисуются поверх других элементов WPF, и они не зависят от z-порядка.</span><span class="sxs-lookup"><span data-stu-id="6eb73-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="6eb73-175">Чтобы увидеть это поведение z-порядка, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="6eb73-176">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="6eb73-177">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-178">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> рисуется над элементом Label.</span><span class="sxs-lookup"><span data-stu-id="6eb73-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="6eb73-179">Закрепление</span><span class="sxs-lookup"><span data-stu-id="6eb73-179">Docking</span></span>

<span data-ttu-id="6eb73-180">элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> поддерживает закрепление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="6eb73-181">Задайте присоединенное свойство <xref:System.Windows.Controls.DockPanel.Dock%2A> для закрепления размещаемого элемента управления в элементе <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="6eb73-182">Чтобы закрепить размещенный элемент управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-183">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="6eb73-184">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-185">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> закреплен на правой стороне элемента <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="6eb73-186">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="6eb73-186">Setting Visibility</span></span>

<span data-ttu-id="6eb73-187">Можно сделать элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] невидимым или свернуть его, задав свойство <xref:System.Windows.UIElement.Visibility%2A> для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-187">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eb73-188">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="6eb73-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="6eb73-189">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="6eb73-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="6eb73-190">Чтобы задать видимость размещенного элемента управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-191">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="6eb73-192">В файле *MainWindow. XAML. vb* или *MainWindow.XAML.CS*скопируйте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="6eb73-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="6eb73-193">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="6eb73-194">Нажмите кнопку, **чтобы сделать невидимую** кнопку, чтобы сделать элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> невидимым.</span><span class="sxs-lookup"><span data-stu-id="6eb73-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="6eb73-195">Нажмите кнопку " **щелкните, чтобы свернуть** ", чтобы полностью скрыть элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> из макета.</span><span class="sxs-lookup"><span data-stu-id="6eb73-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="6eb73-196">При сворачивании элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] окружающие элементы переупорядочиваются, чтобы занять свое пространство.</span><span class="sxs-lookup"><span data-stu-id="6eb73-196">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="6eb73-197">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="6eb73-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="6eb73-198">Некоторые элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют фиксированный размер и не растягиваются для заполнения доступного пространства в макете.</span><span class="sxs-lookup"><span data-stu-id="6eb73-198">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="6eb73-199">Например, элемент управления <xref:System.Windows.Forms.MonthCalendar> отображает месяц в фиксированном пространстве.</span><span class="sxs-lookup"><span data-stu-id="6eb73-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="6eb73-200">Для размещения элемента управления, который не растягивается, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-201">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="6eb73-202">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-203">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> центрируется в строке сетки, но не растягивается для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="6eb73-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="6eb73-204">Если окно достаточно велико, можно увидеть два или больше месяцев, отображаемых размещаемым элементом управления <xref:System.Windows.Forms.MonthCalendar>, но они центрируются по строке.</span><span class="sxs-lookup"><span data-stu-id="6eb73-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="6eb73-205">Подсистема разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выравнивает элементы по центру, размер которых не может быть заполнен для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="6eb73-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="6eb73-206">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="6eb73-206">Scaling</span></span>

<span data-ttu-id="6eb73-207">В отличие от элементов WPF, большинство элементов управления Windows Forms не постоянно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="6eb73-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="6eb73-208">Чтобы обеспечить пользовательское масштабирование, переопределите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6eb73-209">Чтобы масштабировать размещенный элемент управления с использованием поведения по умолчанию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-210">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="6eb73-211">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-212">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="6eb73-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="6eb73-213">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="6eb73-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="6eb73-214">Поворот</span><span class="sxs-lookup"><span data-stu-id="6eb73-214">Rotating</span></span>

<span data-ttu-id="6eb73-215">В отличие от элементов WPF, Windows Forms элементы управления не поддерживают вращение.</span><span class="sxs-lookup"><span data-stu-id="6eb73-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="6eb73-216">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> не поворачивается вместе с другими элементами WPF при применении преобразования поворота.</span><span class="sxs-lookup"><span data-stu-id="6eb73-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="6eb73-217">Любое значение вращения, отличное от 180 градусов, вызывает событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="6eb73-218">Чтобы увидеть результат вращения в гибридном приложении, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-219">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="6eb73-220">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-221">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="6eb73-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="6eb73-222">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="6eb73-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="6eb73-223">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="6eb73-223">Setting Padding and Margins</span></span>

<span data-ttu-id="6eb73-224">Заполнение и поля в макете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] похожи на заполнение и поля в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="6eb73-225">Просто задайте свойства <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="6eb73-226">Чтобы задать заполнение и поля для размещенного элемента управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-227">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="6eb73-228">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-229">Параметры заполнения и поля применяются к размещаемым элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] так же, как и в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-229">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="6eb73-230">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="6eb73-230">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="6eb73-231">предоставляет два динамических контейнера макета: <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-231">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="6eb73-232">Эти контейнеры также можно использовать в макетах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6eb73-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="6eb73-233">Чтобы использовать динамический контейнер макета, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6eb73-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="6eb73-234">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="6eb73-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="6eb73-235">В файле *MainWindow. XAML. vb* или *MainWindow.XAML.CS*скопируйте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="6eb73-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="6eb73-236">Добавьте вызов метода `InitializeFlowLayoutPanel` в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="6eb73-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="6eb73-237">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="6eb73-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="6eb73-238">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> заполняет <xref:System.Windows.Controls.DockPanel>, а <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свои дочерние элементы управления по умолчанию <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="6eb73-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eb73-239">См. также</span><span class="sxs-lookup"><span data-stu-id="6eb73-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6eb73-240">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6eb73-240">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6eb73-241">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="6eb73-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="6eb73-242">Пример упорядочивания элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="6eb73-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- <span data-ttu-id="6eb73-243">[Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="6eb73-243">[Walkthrough: Hosting a Windows Forms Composite Control in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)</span></span>
- <span data-ttu-id="6eb73-244">[Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="6eb73-244">[Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)</span></span>
