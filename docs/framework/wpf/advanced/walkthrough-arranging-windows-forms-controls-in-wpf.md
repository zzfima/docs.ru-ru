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
ms.openlocfilehash: 5b759baebb7192c1ee94b4aa925198864ba7a31a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338778"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="a6ec7-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="a6ec7-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="a6ec7-103">В этом пошаговом руководстве показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функции макета для размещения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в гибридном приложении.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="a6ec7-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="a6ec7-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="a6ec7-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="a6ec7-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="a6ec7-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="a6ec7-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="a6ec7-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="a6ec7-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="a6ec7-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-112">Docking.</span></span>  
  
-   <span data-ttu-id="a6ec7-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="a6ec7-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="a6ec7-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-115">Scaling.</span></span>  
  
-   <span data-ttu-id="a6ec7-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-116">Rotating.</span></span>  
  
-   <span data-ttu-id="a6ec7-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="a6ec7-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="a6ec7-119">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. в разделе [упорядочение Windows Forms в WPF образец](https://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="a6ec7-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="a6ec7-120">Когда вы закончите, вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] возможности разметки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложений на основе.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a6ec7-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a6ec7-121">Prerequisites</span></span>  

<span data-ttu-id="a6ec7-122">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="a6ec7-123">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="a6ec7-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="a6ec7-124">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="a6ec7-124">To create and set up the project</span></span>  
  
1. <span data-ttu-id="a6ec7-125">Создание проекта приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2. <span data-ttu-id="a6ec7-126">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="a6ec7-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="a6ec7-127">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="a6ec7-128">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-128">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="a6ec7-129">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="a6ec7-129">System.Drawing</span></span>  
  
3. <span data-ttu-id="a6ec7-130">Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4. <span data-ttu-id="a6ec7-131">В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="a6ec7-132">В <xref:System.Windows.Controls.Grid> элемент набора <xref:System.Windows.Controls.Grid.ShowGridLines%2A> свойства `true` и определите пять строк и три столбца.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="a6ec7-133">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a6ec7-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="a6ec7-134">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="a6ec7-135">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a6ec7-135">To use default layout settings</span></span>  
  
1. <span data-ttu-id="a6ec7-136">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2. <span data-ttu-id="a6ec7-137">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-138">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Появился на <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="a6ec7-139">Размещаемый элемент управления имеет размер в зависимости от содержимого и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента изменяются, чтобы вместить размещаемый элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="a6ec7-140">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="a6ec7-140">Sizing to Content</span></span>  
 <span data-ttu-id="a6ec7-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещенного элемента управления изменяется в соответствии с правильного отображения его содержимого.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="a6ec7-142">Изменение размеров в соответствии с содержимым</span><span class="sxs-lookup"><span data-stu-id="a6ec7-142">To size to content</span></span>  
  
1. <span data-ttu-id="a6ec7-143">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2. <span data-ttu-id="a6ec7-144">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-145">Два новых элемента управления кнопки изменяется для отображения длинных строк текста и размера шрифта правильно и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементов изменяется, чтобы вместить размещаемые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="a6ec7-146">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="a6ec7-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="a6ec7-147">Абсолютное позиционирование можно использовать для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент в любом месте в пользовательском интерфейсе (UI).</span><span class="sxs-lookup"><span data-stu-id="a6ec7-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="a6ec7-148">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="a6ec7-148">To use absolute positioning</span></span>  
  
1. <span data-ttu-id="a6ec7-149">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2. <span data-ttu-id="a6ec7-150">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент помещается в 20 точках от верхнего края ячейки сетки и в 20 точках от левого края.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="a6ec7-152">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="a6ec7-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="a6ec7-153">Можно указать размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента с помощью <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="a6ec7-154">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="a6ec7-154">To specify size explicitly</span></span>  
  
1. <span data-ttu-id="a6ec7-155">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2. <span data-ttu-id="a6ec7-156">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент имеет значение размером 50 пикселей в ширину и 70 пикселей в высоту, которая меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="a6ec7-158">Содержание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="a6ec7-159">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="a6ec7-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="a6ec7-160">Всегда значение связанные с макетом свойств размещаемого элемента управления с помощью свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a6ec7-161">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="a6ec7-162">Установка связанных с макетом свойств размещаемого элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="a6ec7-163">Чтобы увидеть влияние задания свойств размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-163">To see the effects of setting properties on the hosted control</span></span>  
  
1. <span data-ttu-id="a6ec7-164">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2. <span data-ttu-id="a6ec7-165">В обозревателе решений дважды щелкните файл MainWindow.xaml. vb</span><span class="sxs-lookup"><span data-stu-id="a6ec7-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="a6ec7-166">или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3. <span data-ttu-id="a6ec7-167">Скопируйте следующий код в `MainWindow` определение класса.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="a6ec7-168">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="a6ec7-169">Нажмите кнопку **Click me** кнопки.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-169">Click the **Click me** button.</span></span> <span data-ttu-id="a6ec7-170">`button1_Click` Наборам обработчик событий <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> свойств размещаемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="a6ec7-171">В результате размещаемого элемента управления в границах <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a6ec7-172">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="a6ec7-173">Вместо этого размещаемый элемент управления должен всегда заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="a6ec7-174">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="a6ec7-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="a6ec7-175">Отображается <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других элементов WPF, и это не влияет z порядка.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="a6ec7-176">Чтобы просмотреть это поведение z порядка, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="a6ec7-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="a6ec7-177">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="a6ec7-178">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Окрашивания элемента через элемент метки.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="a6ec7-180">Закрепление</span><span class="sxs-lookup"><span data-stu-id="a6ec7-180">Docking</span></span>
 <span data-ttu-id="a6ec7-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> поддерживает элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепления.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="a6ec7-182">Задайте <xref:System.Windows.Controls.DockPanel.Dock%2A> присоединенного свойства, чтобы закрепить размещаемый элемент управления в <xref:System.Windows.Controls.DockPanel> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="a6ec7-183">Закрепление размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-183">To dock a hosted control</span></span>

1. <span data-ttu-id="a6ec7-184">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="a6ec7-185">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-186"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент закреплен на правой стороне <xref:System.Windows.Controls.DockPanel> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="a6ec7-187">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="a6ec7-187">Setting Visibility</span></span>
 <span data-ttu-id="a6ec7-188">Можно сделать ваши [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления невидимым или свернуть его, задав <xref:System.Windows.UIElement.Visibility%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="a6ec7-189">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="a6ec7-190">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="a6ec7-191">Задание видимости размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="a6ec7-192">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="a6ec7-193">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="a6ec7-194">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="a6ec7-195">Нажмите кнопку **щелкните, чтобы сделать невидимыми** кнопку, чтобы <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент невидимым.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="a6ec7-196">Нажмите кнопку **щелкните, чтобы свернуть** кнопку, чтобы скрыть <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента из макета полностью.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="a6ec7-197">Когда [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления свернут, соседние элементы переупорядочиваются, чтобы занять его место.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="a6ec7-198">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="a6ec7-199">Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного пространства в макете.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="a6ec7-200">Например <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированном пространстве.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="a6ec7-201">Размещение нерастягиваемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="a6ec7-202">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="a6ec7-203">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент выравнивается по центру в строке сетки, но он не растягивается для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="a6ec7-205">Если окно является достаточно большим, можно увидеть два или более месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элемента управления, но они выравниваются по центру в строке.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="a6ec7-206">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Обработчик макетов выравнивает по центру элементы, которые не меняются для заполнения доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="a6ec7-207">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="a6ec7-207">Scaling</span></span>
 <span data-ttu-id="a6ec7-208">В отличие от элементов WPF большинство элементов управления Windows Forms не являются непрерывно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="a6ec7-209">Для предоставления пользовательского масштабирования, переопределить <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="a6ec7-210">Масштабирование размещаемого элемента управления с помощью поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a6ec7-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="a6ec7-211">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="a6ec7-212">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-213">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="a6ec7-214">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="a6ec7-215">Поворот</span><span class="sxs-lookup"><span data-stu-id="a6ec7-215">Rotating</span></span>
 <span data-ttu-id="a6ec7-216">В отличие от элементов WPF элементы управления Windows Forms не поддерживают поворот.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="a6ec7-217"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент поворачивается вместе с другими элементами WPF при применении преобразования поворота.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="a6ec7-218">Значение поворота, отличное от 180 градусов, вызывает <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="a6ec7-219">Чтобы увидеть эффект от поворота в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="a6ec7-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="a6ec7-220">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="a6ec7-221">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-222">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="a6ec7-223">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="a6ec7-224">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="a6ec7-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="a6ec7-225">Отступы и рамки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макета похожи на свои аналоги в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ec7-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="a6ec7-226">Просто задайте <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="a6ec7-227">Задание отбивки и внутренних полей размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="a6ec7-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="a6ec7-228">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="a6ec7-229">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-230">Параметры Отбивки и внутренних полей будут применены к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления таким же образом, они будут применяться в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ec7-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="a6ec7-231">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="a6ec7-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="a6ec7-232">предоставляет два динамических контейнера макета, <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="a6ec7-233">Можно также использовать эти контейнеры в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макетов.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="a6ec7-234">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="a6ec7-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="a6ec7-235">Скопируйте следующий XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="a6ec7-236">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="a6ec7-237">Добавьте вызов метода `InitializeFlowLayoutPanel` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4. <span data-ttu-id="a6ec7-238">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="a6ec7-239"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент заполняет <xref:System.Windows.Controls.DockPanel>, и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы в используемом по умолчанию <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="a6ec7-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ec7-240">См. также</span><span class="sxs-lookup"><span data-stu-id="a6ec7-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a6ec7-241">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6ec7-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a6ec7-242">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="a6ec7-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="a6ec7-243">Элементы управления упорядочение Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="a6ec7-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="a6ec7-244">Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF</span><span class="sxs-lookup"><span data-stu-id="a6ec7-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="a6ec7-245">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6ec7-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
