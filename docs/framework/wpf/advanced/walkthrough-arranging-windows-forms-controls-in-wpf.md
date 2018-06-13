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
ms.openlocfilehash: f2cf82c54724a43a60fb9077c5731d4b4ad2cfd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549663"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="2a9f5-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="2a9f5-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="2a9f5-103">В этом пошаговом руководстве показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностей компоновки для размещения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в гибридных приложениях.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="2a9f5-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="2a9f5-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="2a9f5-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="2a9f5-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="2a9f5-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="2a9f5-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="2a9f5-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="2a9f5-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="2a9f5-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-112">Docking.</span></span>  
  
-   <span data-ttu-id="2a9f5-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="2a9f5-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="2a9f5-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-115">Scaling.</span></span>  
  
-   <span data-ttu-id="2a9f5-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-116">Rotating.</span></span>  
  
-   <span data-ttu-id="2a9f5-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="2a9f5-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="2a9f5-119">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [упорядочение элементов управления Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="2a9f5-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="2a9f5-120">По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] возможности разметки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложений на основе.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a9f5-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2a9f5-121">Prerequisites</span></span>  
 <span data-ttu-id="2a9f5-122">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="2a9f5-123">.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="2a9f5-124">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="2a9f5-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="2a9f5-125">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="2a9f5-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="2a9f5-126">Создание проекта приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="2a9f5-127">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="2a9f5-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="2a9f5-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="2a9f5-129">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="2a9f5-130">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="2a9f5-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="2a9f5-131">Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="2a9f5-132">В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="2a9f5-133">В <xref:System.Windows.Controls.Grid> элемент набора <xref:System.Windows.Controls.Grid.ShowGridLines%2A> свойства `true` и определите пять строк и три столбца.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="2a9f5-134">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a9f5-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="2a9f5-135">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="2a9f5-136">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a9f5-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="2a9f5-137">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="2a9f5-138">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Элемент управления отображается в <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2a9f5-140">Размещенного элемента управления изменяется в зависимости от содержимого и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента изменяются, чтобы вместить размещенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="2a9f5-141">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="2a9f5-141">Sizing to Content</span></span>  
 <span data-ttu-id="2a9f5-142"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещенного элемента управления имеет размер для правильного отображения ее содержимого.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="2a9f5-143">Изменение размеров в соответствии с содержимым</span><span class="sxs-lookup"><span data-stu-id="2a9f5-143">To size to content</span></span>  
  
1.  <span data-ttu-id="2a9f5-144">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="2a9f5-145">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-146">Два новых элемента управления button изменяется для отображения длинных строк текста и размера шрифта правильно и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементов изменяется, чтобы вместить размещаемые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="2a9f5-147">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="2a9f5-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="2a9f5-148">Абсолютное позиционирование используется для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент в любом месте в пользовательском интерфейсе (UI).</span><span class="sxs-lookup"><span data-stu-id="2a9f5-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="2a9f5-149">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="2a9f5-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="2a9f5-150">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="2a9f5-151">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-152"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент помещается 20 пикселей от верхнего края ячейки сетки и 20 пикселей от левого края.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="2a9f5-153">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="2a9f5-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="2a9f5-154">Можно указать размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента с помощью <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="2a9f5-155">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="2a9f5-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="2a9f5-156">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="2a9f5-157">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-158"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент имеет значение 50 пикселей в ширину 70 пикселей в высоту, размер которой меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="2a9f5-159">Содержимое [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="2a9f5-160">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="2a9f5-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="2a9f5-161">Всегда задавать свойства, связанные с макетом размещенного элемента управления, с помощью свойств <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="2a9f5-162">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="2a9f5-163">Установка свойства, связанные с макетом размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не делает ничего.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="2a9f5-164">Чтобы увидеть влияние задания свойств размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="2a9f5-165">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="2a9f5-166">В обозревателе решений дважды щелкните файл MainWindow.xaml. vb</span><span class="sxs-lookup"><span data-stu-id="2a9f5-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="2a9f5-167">или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="2a9f5-168">Скопируйте следующий код в `MainWindow` определения класса.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="2a9f5-169">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="2a9f5-170">Нажмите кнопку **Click me** кнопки.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-170">Click the **Click me** button.</span></span> <span data-ttu-id="2a9f5-171">`button1_Click` Задает обработчик событий <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> свойства размещенным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="2a9f5-172">В результате размещенного элемента управления изменять внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="2a9f5-173">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="2a9f5-174">Вместо этого размещаемый элемент управления должен всегда заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="2a9f5-175">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="2a9f5-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="2a9f5-176">Отображается <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других элементов WPF, и они не затрагиваются с z порядком.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-176">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="2a9f5-177">Чтобы увидеть это z порядка, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2a9f5-177">To see this z-order behavior, do the following:</span></span>

1.  <span data-ttu-id="2a9f5-178">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-178">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
 
2.  <span data-ttu-id="2a9f5-179">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-179">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент рисуется через элемент label.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-180">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  


## <a name="docking"></a><span data-ttu-id="2a9f5-181">Закрепление</span><span class="sxs-lookup"><span data-stu-id="2a9f5-181">Docking</span></span>  
 <span data-ttu-id="2a9f5-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> поддерживает элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепления.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-182"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="2a9f5-183">Задать <xref:System.Windows.Controls.DockPanel.Dock%2A> вложенное свойство, чтобы закрепить размещенного элемента управления в <xref:System.Windows.Controls.DockPanel> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-183">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="2a9f5-184">Закрепление размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-184">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="2a9f5-185">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-185">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="2a9f5-186">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-186">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент закреплен в правую часть <xref:System.Windows.Controls.DockPanel> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-187">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="2a9f5-188">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="2a9f5-188">Setting Visibility</span></span>  
 <span data-ttu-id="2a9f5-189">Можно сделать ваш [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления невидимым или свернуть его, задав <xref:System.Windows.UIElement.Visibility%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-189">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="2a9f5-190">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-190">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="2a9f5-191">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-191">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="2a9f5-192">Задание видимости размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-192">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="2a9f5-193">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-193">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="2a9f5-194">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-194">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="2a9f5-195">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-195">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="2a9f5-196">Нажмите кнопку **щелкните, чтобы сделать невидимыми** кнопку, чтобы <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент невидимым.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-196">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="2a9f5-197">Нажмите кнопку **щелкните, чтобы свернуть** кнопку, чтобы скрыть <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент из макета полностью.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-197">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="2a9f5-198">Когда [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления свернут, соседние элементы переупорядочиваются, чтобы занять его место.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-198">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="2a9f5-199">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-199">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="2a9f5-200">Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного места в макете.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-200">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="2a9f5-201">Например <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированное пространство.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-201">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="2a9f5-202">Размещение нерастягиваемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-202">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="2a9f5-203">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-203">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="2a9f5-204">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-204">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-205"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемента выравнивается по центру в строке сетки, но она не растягивается для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-205">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="2a9f5-206">Если окно является достаточно большим, можно увидеть два или более месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элемента управления, но они выравниваются по центру в строке.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-206">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="2a9f5-207">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Обработчик макетов Центрирование элементов, которые не меняются для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-207">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="2a9f5-208">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="2a9f5-208">Scaling</span></span>  
 <span data-ttu-id="2a9f5-209">В отличие от элементов WPF большинство элементов управления Windows Forms не являются непрерывно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-209">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="2a9f5-210">Для предоставления пользовательского масштабирования, переопределите <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-210">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span> 
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="2a9f5-211">Масштабирование размещаемого элемента управления с помощью поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="2a9f5-211">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="2a9f5-212">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-212">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="2a9f5-213">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-213">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-214">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-214">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="2a9f5-215">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-215">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="2a9f5-216">Поворот</span><span class="sxs-lookup"><span data-stu-id="2a9f5-216">Rotating</span></span>  
 <span data-ttu-id="2a9f5-217">В отличие от элементов WPF элементы управления Windows Forms не поддерживают поворот.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-217">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="2a9f5-218"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент не поворот с другими элементами WPF, когда применяется преобразование поворота.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-218">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="2a9f5-219">Значение поворота, отличное от 180 градусов, вызывает <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-219">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>
 
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="2a9f5-220">Чтобы увидеть эффект от поворота в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="2a9f5-220">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="2a9f5-221">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-221">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="2a9f5-222">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-222">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-223">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-223">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="2a9f5-224">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-224">You may have to resize the window to see the elements.</span></span>  
 

## <a name="setting-padding-and-margins"></a><span data-ttu-id="2a9f5-225">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="2a9f5-225">Setting Padding and Margins</span></span>  
 <span data-ttu-id="2a9f5-226">Заполнение и поля в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макета аналогичны отступы и рамки, в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a9f5-226">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="2a9f5-227">Просто установите <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-227">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="2a9f5-228">Задание отбивки и внутренних полей размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="2a9f5-228">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="2a9f5-229">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-229">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="2a9f5-230">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-230">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-231">Параметры поля и заполнение применяются к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления таким же образом, как они будут применяться в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a9f5-231">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="2a9f5-232">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="2a9f5-232">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="2a9f5-233"> предусмотрены два типа контейнеров динамического макета, <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-233"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="2a9f5-234">Можно также использовать эти контейнеры в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макеты.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-234">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="2a9f5-235">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="2a9f5-235">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="2a9f5-236">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-236">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="2a9f5-237">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-237">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="2a9f5-238">Добавьте вызов `InitializeFlowLayoutPanel` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-238">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="2a9f5-239">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-239">Press F5 to build and run the application.</span></span> <span data-ttu-id="2a9f5-240"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Заполняет элемент <xref:System.Windows.Controls.DockPanel>, и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы в значение по умолчанию <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a9f5-240">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9f5-241">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9f5-241">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="2a9f5-242">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="2a9f5-242">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="2a9f5-243">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="2a9f5-243">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="2a9f5-244">Элементы управления упорядочение Windows Forms в образце WPF</span><span class="sxs-lookup"><span data-stu-id="2a9f5-244">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="2a9f5-245">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="2a9f5-245">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="2a9f5-246">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a9f5-246">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
