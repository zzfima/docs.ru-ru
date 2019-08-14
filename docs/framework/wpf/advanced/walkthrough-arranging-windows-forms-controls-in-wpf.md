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
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972309"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="71ffb-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="71ffb-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="71ffb-103">В этом пошаговом руководстве показано [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , как использовать функции [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] макета для упорядочения элементов управления в гибридном приложении.</span><span class="sxs-lookup"><span data-stu-id="71ffb-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="71ffb-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="71ffb-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="71ffb-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="71ffb-105">Creating the project.</span></span>

- <span data-ttu-id="71ffb-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71ffb-106">Using default layout settings.</span></span>

- <span data-ttu-id="71ffb-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="71ffb-107">Sizing to content.</span></span>

- <span data-ttu-id="71ffb-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="71ffb-108">Using absolute positioning.</span></span>

- <span data-ttu-id="71ffb-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="71ffb-109">Specifying size explicitly.</span></span>

- <span data-ttu-id="71ffb-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="71ffb-110">Setting layout properties.</span></span>

- <span data-ttu-id="71ffb-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="71ffb-111">Understanding z-order limitations.</span></span>

- <span data-ttu-id="71ffb-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="71ffb-112">Docking.</span></span>

- <span data-ttu-id="71ffb-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="71ffb-113">Setting visibility.</span></span>

- <span data-ttu-id="71ffb-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="71ffb-114">Hosting a control that does not stretch.</span></span>

- <span data-ttu-id="71ffb-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="71ffb-115">Scaling.</span></span>

- <span data-ttu-id="71ffb-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="71ffb-116">Rotating.</span></span>

- <span data-ttu-id="71ffb-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="71ffb-117">Setting padding and margins.</span></span>

- <span data-ttu-id="71ffb-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="71ffb-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="71ffb-119">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Размещение элементов управления Windows Forms в WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="71ffb-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="71ffb-120">По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] функциях макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложениях на основе.</span><span class="sxs-lookup"><span data-stu-id="71ffb-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="71ffb-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="71ffb-121">Prerequisites</span></span>

<span data-ttu-id="71ffb-122">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="71ffb-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="71ffb-123">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="71ffb-123">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="71ffb-124">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="71ffb-124">To create and set up the project</span></span>

1. <span data-ttu-id="71ffb-125">Создайте проект приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="71ffb-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="71ffb-126">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="71ffb-126">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="71ffb-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="71ffb-127">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="71ffb-128">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="71ffb-128">System.Windows.Forms</span></span>

    - <span data-ttu-id="71ffb-129">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="71ffb-129">System.Drawing</span></span>

3. <span data-ttu-id="71ffb-130">Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="71ffb-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>

4. <span data-ttu-id="71ffb-131">В элементе добавьте следующее [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен. <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="71ffb-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="71ffb-132">В элементе задайте для`true` свойства значение и определите пять строк и три столбца. <xref:System.Windows.Controls.Grid.ShowGridLines%2A> <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="71ffb-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="71ffb-133">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="71ffb-133">Using Default Layout Settings</span></span>

<span data-ttu-id="71ffb-134">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещенного [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="71ffb-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-use-default-layout-settings"></a><span data-ttu-id="71ffb-135">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="71ffb-135">To use default layout settings</span></span>

1. <span data-ttu-id="71ffb-136">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="71ffb-137">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-138">Элемент управления появится в<xref:System.Windows.Controls.Canvas>. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="71ffb-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="71ffb-139">Размер размещаемого элемента управления зависит от его содержимого, и <xref:System.Windows.Forms.Integration.WindowsFormsHost> размер элемента изменяется в соответствии с размещаемым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="71ffb-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="71ffb-140">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="71ffb-140">Sizing to Content</span></span>

<span data-ttu-id="71ffb-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещаемый элемент управления будет иметь размер для правильного вывода его содержимого.</span><span class="sxs-lookup"><span data-stu-id="71ffb-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

### <a name="to-size-to-content"></a><span data-ttu-id="71ffb-142">Изменение размеров в соответствии с содержимым</span><span class="sxs-lookup"><span data-stu-id="71ffb-142">To size to content</span></span>

1. <span data-ttu-id="71ffb-143">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="71ffb-144">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-145">Два новых элемента управления "Кнопка" имеют размеры, чтобы правильно отображать более длинную текстовую строку и больший <xref:System.Windows.Forms.Integration.WindowsFormsHost> размер шрифта, а размеры элементов изменялись в соответствии с размещаемыми элементами управления.</span><span class="sxs-lookup"><span data-stu-id="71ffb-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="71ffb-146">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="71ffb-146">Using Absolute Positioning</span></span>

<span data-ttu-id="71ffb-147">Можно использовать абсолютное позиционирование для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента в любом месте пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="71ffb-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

### <a name="to-use-absolute-positioning"></a><span data-ttu-id="71ffb-148">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="71ffb-148">To use absolute positioning</span></span>

1. <span data-ttu-id="71ffb-149">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="71ffb-150">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент размещается на 20 пикселях с верхней стороны ячейки сетки и на 20 пикселях слева.</span><span class="sxs-lookup"><span data-stu-id="71ffb-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="71ffb-152">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="71ffb-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="71ffb-153">Размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента можно указать <xref:System.Windows.FrameworkElement.Width%2A> с помощью свойств и <xref:System.Windows.FrameworkElement.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="71ffb-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

### <a name="to-specify-size-explicitly"></a><span data-ttu-id="71ffb-154">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="71ffb-154">To specify size explicitly</span></span>

1. <span data-ttu-id="71ffb-155">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="71ffb-156">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-157">Для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента задается размер в 50 пикселей в ширину на 70 пикселей высотой, что меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71ffb-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="71ffb-158">Содержимое [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="71ffb-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="71ffb-159">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="71ffb-159">Setting Layout Properties</span></span>

<span data-ttu-id="71ffb-160">Всегда устанавливайте связанные с макетом свойства размещаемого элемента управления с помощью свойств <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="71ffb-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="71ffb-161">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="71ffb-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="71ffb-162">Установка свойств, связанных с макетом, для размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="71ffb-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="71ffb-163">Чтобы увидеть влияние задания свойств размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-163">To see the effects of setting properties on the hosted control</span></span>

1. <span data-ttu-id="71ffb-164">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="71ffb-165">В обозревателе решений дважды щелкните файл MainWindow.xaml. vb</span><span class="sxs-lookup"><span data-stu-id="71ffb-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="71ffb-166">или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="71ffb-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>

3. <span data-ttu-id="71ffb-167">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="71ffb-167">Copy the following code into the `MainWindow` class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="71ffb-168">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="71ffb-169">Нажмите кнопку " **щелкните мне** ".</span><span class="sxs-lookup"><span data-stu-id="71ffb-169">Click the **Click me** button.</span></span> <span data-ttu-id="71ffb-170">Обработчик событий задает свойства <xref:System.Windows.Forms.Control.Left%2A>идля размещаемого элемента управления. <xref:System.Windows.Forms.Control.Top%2A> `button1_Click`</span><span class="sxs-lookup"><span data-stu-id="71ffb-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="71ffb-171">В результате размещаемый элемент управления будет перемещен в пределах <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="71ffb-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="71ffb-172">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="71ffb-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="71ffb-173">Вместо этого размещаемый элемент управления всегда должен заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="71ffb-174">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="71ffb-174">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="71ffb-175">Видимые <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других элементов WPF и не зависят от z-порядка.</span><span class="sxs-lookup"><span data-stu-id="71ffb-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="71ffb-176">Чтобы увидеть это поведение z-порядка, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71ffb-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="71ffb-177">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="71ffb-178">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент зарисовывается поверх элемента Label.</span><span class="sxs-lookup"><span data-stu-id="71ffb-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="71ffb-180">Закрепление</span><span class="sxs-lookup"><span data-stu-id="71ffb-180">Docking</span></span>

<span data-ttu-id="71ffb-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost>элемент поддерживает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепление.</span><span class="sxs-lookup"><span data-stu-id="71ffb-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="71ffb-182">Задайте присоединенное свойство, чтобы закрепить размещенный <xref:System.Windows.Controls.DockPanel> элемент управления в элементе. <xref:System.Windows.Controls.DockPanel.Dock%2A></span><span class="sxs-lookup"><span data-stu-id="71ffb-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="71ffb-183">Закрепление размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-183">To dock a hosted control</span></span>

1. <span data-ttu-id="71ffb-184">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="71ffb-185">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-186">Элемент закреплен с правой стороны <xref:System.Windows.Controls.DockPanel> элемента. <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="71ffb-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="71ffb-187">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="71ffb-187">Setting Visibility</span></span>

<span data-ttu-id="71ffb-188">Можно сделать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления невидимым или свернуть его, <xref:System.Windows.UIElement.Visibility%2A> задав свойство для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="71ffb-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="71ffb-189">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="71ffb-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="71ffb-190">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="71ffb-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="71ffb-191">Задание видимости размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="71ffb-192">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="71ffb-193">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="71ffb-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="71ffb-194">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="71ffb-195">Нажмите кнопку " **щелкните, чтобы сделать** невидимой <xref:System.Windows.Forms.Integration.WindowsFormsHost> кнопку", чтобы сделать элемент невидимым.</span><span class="sxs-lookup"><span data-stu-id="71ffb-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="71ffb-196">Нажмите кнопку " **щелкните, чтобы свернуть** ", <xref:System.Windows.Forms.Integration.WindowsFormsHost> чтобы полностью скрыть элемент в макете.</span><span class="sxs-lookup"><span data-stu-id="71ffb-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="71ffb-197">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Когда элемент управления сворачивается, окружающие его элементы переупорядочиваются, чтобы занять свое пространство.</span><span class="sxs-lookup"><span data-stu-id="71ffb-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="71ffb-198">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-198">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="71ffb-199">Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного пространства в макете.</span><span class="sxs-lookup"><span data-stu-id="71ffb-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="71ffb-200">Например, <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированном пространстве.</span><span class="sxs-lookup"><span data-stu-id="71ffb-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="71ffb-201">Размещение нерастягиваемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="71ffb-202">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="71ffb-203">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент выравнивается по центру в строке сетки, но не растягивается для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="71ffb-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="71ffb-205">Если окно достаточно велико, можно увидеть два или больше месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элементом управления, но они центрируются по строке.</span><span class="sxs-lookup"><span data-stu-id="71ffb-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="71ffb-206">Обработчик [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макетов выравнивает элементы, размер которых не может быть заполнять доступное пространство.</span><span class="sxs-lookup"><span data-stu-id="71ffb-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="71ffb-207">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="71ffb-207">Scaling</span></span>

<span data-ttu-id="71ffb-208">В отличие от элементов WPF, большинство элементов управления Windows Forms не постоянно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="71ffb-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="71ffb-209">Чтобы обеспечить настраиваемое масштабирование, необходимо <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> переопределить метод.</span><span class="sxs-lookup"><span data-stu-id="71ffb-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="71ffb-210">Масштабирование размещаемого элемента управления с помощью поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="71ffb-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="71ffb-211">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="71ffb-212">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-213">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="71ffb-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="71ffb-214">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="71ffb-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="71ffb-215">Поворот</span><span class="sxs-lookup"><span data-stu-id="71ffb-215">Rotating</span></span>

<span data-ttu-id="71ffb-216">В отличие от элементов WPF, Windows Forms элементы управления не поддерживают вращение.</span><span class="sxs-lookup"><span data-stu-id="71ffb-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="71ffb-217"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент не поворачивается с другими элементами WPF при применении преобразования поворота.</span><span class="sxs-lookup"><span data-stu-id="71ffb-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="71ffb-218">Любое значение вращения, отличное от 180 градусов, <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="71ffb-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="71ffb-219">Чтобы увидеть эффект от поворота в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="71ffb-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="71ffb-220">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="71ffb-221">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-222">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="71ffb-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="71ffb-223">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="71ffb-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="71ffb-224">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="71ffb-224">Setting Padding and Margins</span></span>

<span data-ttu-id="71ffb-225">Заполнение и поля в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макете похожи на заполнение и поля в. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ffb-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="71ffb-226">Просто задайте <xref:System.Windows.Controls.Control.Padding%2A> свойства и <xref:System.Windows.FrameworkElement.Margin%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="71ffb-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="71ffb-227">Задание отбивки и внутренних полей размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="71ffb-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="71ffb-228">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="71ffb-229">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-230">Параметры заполнения и поля применяются к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементам управления так же, как и в. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ffb-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="71ffb-231">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="71ffb-231">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="71ffb-232">предоставляет два динамических контейнера макета: <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="71ffb-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="71ffb-233">Эти контейнеры также можно использовать в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макетах.</span><span class="sxs-lookup"><span data-stu-id="71ffb-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="71ffb-234">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="71ffb-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="71ffb-235">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="71ffb-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="71ffb-236">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="71ffb-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="71ffb-237">Добавьте вызов метода `InitializeFlowLayoutPanel` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="71ffb-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="71ffb-238">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="71ffb-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="71ffb-239">Элемент заполняет объект <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы управления по умолчанию. <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="71ffb-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="71ffb-240">См. также</span><span class="sxs-lookup"><span data-stu-id="71ffb-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="71ffb-241">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="71ffb-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="71ffb-242">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="71ffb-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="71ffb-243">Пример упорядочивания элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="71ffb-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="71ffb-244">Пошаговое руководство: Размещение составного элемента управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="71ffb-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="71ffb-245">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71ffb-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
