---
title: Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 484895db539b288bf388ff6c2ce3c29db55080b1
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197838"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="ff906-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="ff906-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="ff906-103">В этом пошаговом руководстве показано, как использовать функции макета [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для упорядочения элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] в гибридном приложении.</span><span class="sxs-lookup"><span data-stu-id="ff906-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="ff906-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ff906-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ff906-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="ff906-105">Creating the project.</span></span>
- <span data-ttu-id="ff906-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff906-106">Using default layout settings.</span></span>
- <span data-ttu-id="ff906-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="ff906-107">Sizing to content.</span></span>
- <span data-ttu-id="ff906-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="ff906-108">Using absolute positioning.</span></span>
- <span data-ttu-id="ff906-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="ff906-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="ff906-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="ff906-110">Setting layout properties.</span></span>
- <span data-ttu-id="ff906-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="ff906-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="ff906-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="ff906-112">Docking.</span></span>
- <span data-ttu-id="ff906-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="ff906-113">Setting visibility.</span></span>
- <span data-ttu-id="ff906-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="ff906-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="ff906-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="ff906-115">Scaling.</span></span>
- <span data-ttu-id="ff906-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="ff906-116">Rotating.</span></span>
- <span data-ttu-id="ff906-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="ff906-117">Setting padding and margins.</span></span>
- <span data-ttu-id="ff906-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="ff906-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="ff906-119">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Размещение элементов управления Windows Forms в WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="ff906-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="ff906-120">По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ных функциях макета в приложениях на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ff906-121">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="ff906-121">Prerequisites</span></span>

<span data-ttu-id="ff906-122">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ff906-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="ff906-123">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ff906-123">Creating the Project</span></span>

<span data-ttu-id="ff906-124">Чтобы создать и настроить проект, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="ff906-125">Создайте проект приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="ff906-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="ff906-126">В обозреватель решений добавьте ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="ff906-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="ff906-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ff906-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="ff906-128">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ff906-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="ff906-129">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="ff906-129">System.Drawing</span></span>

3. <span data-ttu-id="ff906-130">Дважды щелкните файл *MainWindow. XAML* , чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="ff906-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="ff906-131">В элемент <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="ff906-132">В элементе <xref:System.Windows.Controls.Grid> задайте для свойства <xref:System.Windows.Controls.Grid.ShowGridLines%2A> значение `true` и определите пять строк и три столбца.</span><span class="sxs-lookup"><span data-stu-id="ff906-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="ff906-133">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ff906-133">Using Default Layout Settings</span></span>

<span data-ttu-id="ff906-134">По умолчанию элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> обрабатывает макет для размещенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="ff906-135">Чтобы использовать параметры макета по умолчанию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="ff906-136">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="ff906-137">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-138">В <xref:System.Windows.Controls.Canvas>появится элемент управления <xref:System.Windows.Forms.Button?displayProperty=nameWithType> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="ff906-139">Размер размещаемого элемента управления зависит от его содержимого, а размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяется в соответствии с размещаемым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="ff906-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="ff906-140">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="ff906-140">Sizing to Content</span></span>

<span data-ttu-id="ff906-141">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> гарантирует, что размещаемый элемент управления будет иметь размер для правильного вывода его содержимого.</span><span class="sxs-lookup"><span data-stu-id="ff906-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="ff906-142">Чтобы задать размер содержимого, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="ff906-143">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="ff906-144">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-145">Два новых элемента управления "Кнопка" имеют размер, чтобы правильно отображать более длинную текстовую строку и больший размер шрифта, а размеры элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost> изменяются в соответствии с размещаемыми элементами управления.</span><span class="sxs-lookup"><span data-stu-id="ff906-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="ff906-146">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="ff906-146">Using Absolute Positioning</span></span>

<span data-ttu-id="ff906-147">Можно использовать абсолютное позиционирование для размещения элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> в любом месте пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ff906-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="ff906-148">Чтобы использовать абсолютное позиционирование, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="ff906-149">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="ff906-150">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-151">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> размещается на 20 пикселях с верхней стороны ячейки сетки и на 20 пикселях слева.</span><span class="sxs-lookup"><span data-stu-id="ff906-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="ff906-152">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="ff906-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="ff906-153">Размер элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> можно указать с помощью свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff906-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="ff906-154">Чтобы указать размер явным образом, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="ff906-155">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="ff906-156">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-157">Для элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> задается размер 50 пикселей в ширину на 70 пикселей выше, что меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff906-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="ff906-158">Содержимое элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="ff906-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="ff906-159">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="ff906-159">Setting Layout Properties</span></span>

<span data-ttu-id="ff906-160">Всегда устанавливайте связанные с макетом свойства размещаемого элемента управления с помощью свойств элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="ff906-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ff906-161">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="ff906-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="ff906-162">Установка свойств, связанных с макетом, для размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="ff906-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="ff906-163">Чтобы увидеть влияние установки свойств на размещенном элементе управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="ff906-164">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="ff906-165">В **Обозреватель решений**дважды щелкните файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS* , чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="ff906-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="ff906-166">Скопируйте следующий код в определение класса `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="ff906-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="ff906-167">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="ff906-168">Нажмите кнопку " **щелкните мне** ".</span><span class="sxs-lookup"><span data-stu-id="ff906-168">Click the **Click me** button.</span></span> <span data-ttu-id="ff906-169">Обработчик событий `button1_Click` задает свойства <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> размещаемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ff906-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="ff906-170">Это приводит к перемещению размещенного элемента управления в элементе <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="ff906-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ff906-171">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="ff906-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="ff906-172">Вместо этого размещаемый элемент управления всегда должен заполнять элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="ff906-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="ff906-173">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="ff906-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="ff906-174">Видимые <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других элементов WPF и не зависят от z-порядка.</span><span class="sxs-lookup"><span data-stu-id="ff906-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="ff906-175">Чтобы увидеть это поведение z-порядка, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="ff906-176">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="ff906-177">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-178">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> зарисовывается поверх элемента Label.</span><span class="sxs-lookup"><span data-stu-id="ff906-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="ff906-179">Закрепление</span><span class="sxs-lookup"><span data-stu-id="ff906-179">Docking</span></span>

<span data-ttu-id="ff906-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент поддерживает закрепление [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="ff906-181">Задайте присоединенное свойство <xref:System.Windows.Controls.DockPanel.Dock%2A>, чтобы закрепить размещаемый элемент управления в элементе <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="ff906-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="ff906-182">Чтобы закрепить размещенный элемент управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="ff906-183">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="ff906-184">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-185">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> закреплен в правой части элемента <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="ff906-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="ff906-186">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="ff906-186">Setting Visibility</span></span>

<span data-ttu-id="ff906-187">Можно сделать элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] невидимым или свернуть его, установив свойство <xref:System.Windows.UIElement.Visibility%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="ff906-187">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="ff906-188">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="ff906-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="ff906-189">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="ff906-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="ff906-190">Чтобы задать видимость размещенного элемента управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="ff906-191">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="ff906-192">В файле *MainWindow. XAML. vb* или *MainWindow.XAML.CS*скопируйте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="ff906-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="ff906-193">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="ff906-194">Нажмите кнопку, **чтобы сделать невидимой** кнопку, чтобы сделать элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> невидимым.</span><span class="sxs-lookup"><span data-stu-id="ff906-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="ff906-195">Нажмите кнопку " **щелкните, чтобы свернуть** ", чтобы полностью скрыть элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> из макета.</span><span class="sxs-lookup"><span data-stu-id="ff906-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="ff906-196">Когда элемент управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сворачивается, окружающие элементы переупорядочиваются, чтобы занять свое пространство.</span><span class="sxs-lookup"><span data-stu-id="ff906-196">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="ff906-197">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="ff906-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="ff906-198">Некоторые элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют фиксированный размер и не растягиваются для заполнения доступного пространства в макете.</span><span class="sxs-lookup"><span data-stu-id="ff906-198">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="ff906-199">Например, элемент управления <xref:System.Windows.Forms.MonthCalendar> отображает месяц в фиксированном пространстве.</span><span class="sxs-lookup"><span data-stu-id="ff906-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="ff906-200">Для размещения элемента управления, который не растягивается, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="ff906-201">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="ff906-202">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-203">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> выравнивается по центру в строке сетки, но не растягивается для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="ff906-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="ff906-204">Если окно достаточно велико, можно увидеть два или больше месяцев, отображаемых размещаемым элементом управления <xref:System.Windows.Forms.MonthCalendar>, но они находятся в центре строки.</span><span class="sxs-lookup"><span data-stu-id="ff906-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="ff906-205">Подсистема разметки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] выравнивает элементы, размер которых не может быть заполнять доступное пространство.</span><span class="sxs-lookup"><span data-stu-id="ff906-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="ff906-206">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="ff906-206">Scaling</span></span>

<span data-ttu-id="ff906-207">В отличие от элементов WPF, большинство элементов управления Windows Forms не постоянно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="ff906-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="ff906-208">Чтобы обеспечить пользовательское масштабирование, переопределите метод <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ff906-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="ff906-209">Чтобы масштабировать размещенный элемент управления с использованием поведения по умолчанию, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="ff906-210">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="ff906-211">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-212">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="ff906-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="ff906-213">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="ff906-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="ff906-214">Поворот</span><span class="sxs-lookup"><span data-stu-id="ff906-214">Rotating</span></span>

<span data-ttu-id="ff906-215">В отличие от элементов WPF, Windows Forms элементы управления не поддерживают вращение.</span><span class="sxs-lookup"><span data-stu-id="ff906-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="ff906-216">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> не поворачивается вместе с другими элементами WPF при применении преобразования «вращение».</span><span class="sxs-lookup"><span data-stu-id="ff906-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="ff906-217">Любое значение вращения, отличное от 180 градусов, вызывает событие <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>.</span><span class="sxs-lookup"><span data-stu-id="ff906-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="ff906-218">Чтобы увидеть результат вращения в гибридном приложении, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="ff906-219">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="ff906-220">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-221">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="ff906-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="ff906-222">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="ff906-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="ff906-223">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="ff906-223">Setting Padding and Margins</span></span>

<span data-ttu-id="ff906-224">Заполнение и поля в макете [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] похожи на заполнение и поля в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="ff906-225">Просто задайте свойства <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="ff906-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="ff906-226">Чтобы задать заполнение и поля для размещенного элемента управления, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="ff906-227">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="ff906-228">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-229">Параметры заполнения и поля применяются к размещенным элементам управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] так же, как они будут применяться в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-229">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="ff906-230">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="ff906-230">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="ff906-231">предоставляет два динамических контейнера макета: <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="ff906-231">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="ff906-232">Эти контейнеры также можно использовать в макетах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff906-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="ff906-233">Чтобы использовать динамический контейнер макета, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ff906-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="ff906-234">Скопируйте следующий код XAML в элемент <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ff906-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="ff906-235">В файле *MainWindow. XAML. vb* или *MainWindow.XAML.CS*скопируйте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="ff906-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="ff906-236">Добавьте вызов метода `InitializeFlowLayoutPanel` в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="ff906-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="ff906-237">Нажмите клавишу <kbd>F5</kbd>, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ff906-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="ff906-238">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> заполняет <xref:System.Windows.Controls.DockPanel>и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает свои дочерние элементы управления в <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff906-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff906-239">См. также</span><span class="sxs-lookup"><span data-stu-id="ff906-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ff906-240">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff906-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="ff906-241">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="ff906-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="ff906-242">Пример упорядочивания элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="ff906-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="ff906-243">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="ff906-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="ff906-244">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff906-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
