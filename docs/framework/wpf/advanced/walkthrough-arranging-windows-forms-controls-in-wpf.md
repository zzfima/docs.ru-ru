---
title: "Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF"
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
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 480d61f6ca2aa67e0de48030655a6368c70554f4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="26b7a-102">Пошаговое руководство. Упорядочение элементов управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="26b7a-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="26b7a-103">В этом пошаговом руководстве показано, как использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностей компоновки для размещения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в гибридных приложениях.</span><span class="sxs-lookup"><span data-stu-id="26b7a-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="26b7a-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="26b7a-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="26b7a-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="26b7a-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="26b7a-106">Использование параметров макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26b7a-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="26b7a-107">Изменение размеров в зависимости от содержимого.</span><span class="sxs-lookup"><span data-stu-id="26b7a-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="26b7a-108">Использование абсолютного позиционирования.</span><span class="sxs-lookup"><span data-stu-id="26b7a-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="26b7a-109">Задание размера явным образом.</span><span class="sxs-lookup"><span data-stu-id="26b7a-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="26b7a-110">Установка свойств макета.</span><span class="sxs-lookup"><span data-stu-id="26b7a-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="26b7a-111">Описание ограничений z-порядка.</span><span class="sxs-lookup"><span data-stu-id="26b7a-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="26b7a-112">Закрепление.</span><span class="sxs-lookup"><span data-stu-id="26b7a-112">Docking.</span></span>  
  
-   <span data-ttu-id="26b7a-113">Задание видимости.</span><span class="sxs-lookup"><span data-stu-id="26b7a-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="26b7a-114">Размещение нерастягиваемых элементов управления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="26b7a-115">Масштабирование.</span><span class="sxs-lookup"><span data-stu-id="26b7a-115">Scaling.</span></span>  
  
-   <span data-ttu-id="26b7a-116">Поворот.</span><span class="sxs-lookup"><span data-stu-id="26b7a-116">Rotating.</span></span>  
  
-   <span data-ttu-id="26b7a-117">Задание полей и внутренних полей.</span><span class="sxs-lookup"><span data-stu-id="26b7a-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="26b7a-118">Использование динамических контейнеров макета.</span><span class="sxs-lookup"><span data-stu-id="26b7a-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="26b7a-119">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [упорядочение элементов управления Windows Forms в образце WPF](http://go.microsoft.com/fwlink/?LinkID=159971).</span><span class="sxs-lookup"><span data-stu-id="26b7a-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="26b7a-120">По завершении вы получите представление о [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] возможности разметки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложений на основе.</span><span class="sxs-lookup"><span data-stu-id="26b7a-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26b7a-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="26b7a-121">Prerequisites</span></span>  
 <span data-ttu-id="26b7a-122">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="26b7a-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="26b7a-123">.</span><span class="sxs-lookup"><span data-stu-id="26b7a-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="26b7a-124">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="26b7a-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="26b7a-125">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="26b7a-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="26b7a-126">Создание проекта приложения WPF с именем `WpfLayoutHostingWf`.</span><span class="sxs-lookup"><span data-stu-id="26b7a-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="26b7a-127">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="26b7a-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="26b7a-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="26b7a-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="26b7a-129">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="26b7a-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="26b7a-130">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="26b7a-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="26b7a-131">Дважды щелкните файл MainWindow.xaml, чтобы открыть его в представлении XAML.</span><span class="sxs-lookup"><span data-stu-id="26b7a-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="26b7a-132">В <xref:System.Windows.Window> элемента, добавьте следующий [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="26b7a-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="26b7a-133">В <xref:System.Windows.Controls.Grid> элемент набора <xref:System.Windows.Controls.Grid.ShowGridLines%2A> свойства `true` и определите пять строк и три столбца.</span><span class="sxs-lookup"><span data-stu-id="26b7a-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="26b7a-134">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="26b7a-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="26b7a-135">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент обрабатывает макет для размещаемого [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="26b7a-136">Использование параметров макета по умолчанию</span><span class="sxs-lookup"><span data-stu-id="26b7a-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="26b7a-137">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="26b7a-138">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> Элемент управления отображается в <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="26b7a-140">Размещенного элемента управления изменяется в зависимости от содержимого и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента изменяются, чтобы вместить размещенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="26b7a-141">Изменение размеров в зависимости от содержимого</span><span class="sxs-lookup"><span data-stu-id="26b7a-141">Sizing to Content</span></span>  
 <span data-ttu-id="26b7a-142"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент гарантирует, что размещенного элемента управления имеет размер для правильного отображения ее содержимого.</span><span class="sxs-lookup"><span data-stu-id="26b7a-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="26b7a-143">Изменение размеров в соответствии с содержимым</span><span class="sxs-lookup"><span data-stu-id="26b7a-143">To size to content</span></span>  
  
1.  <span data-ttu-id="26b7a-144">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="26b7a-145">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-146">Два новых элемента управления button изменяется для отображения длинных строк текста и размера шрифта правильно и <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементов изменяется, чтобы вместить размещаемые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="26b7a-147">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="26b7a-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="26b7a-148">Абсолютное позиционирование используется для размещения <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент в любом месте в пользовательском интерфейсе (UI).</span><span class="sxs-lookup"><span data-stu-id="26b7a-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="26b7a-149">Использование абсолютного позиционирования</span><span class="sxs-lookup"><span data-stu-id="26b7a-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="26b7a-150">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="26b7a-151">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-152"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент помещается 20 пикселей от верхнего края ячейки сетки и 20 пикселей от левого края.</span><span class="sxs-lookup"><span data-stu-id="26b7a-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="26b7a-153">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="26b7a-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="26b7a-154">Можно указать размер <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента с помощью <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="26b7a-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="26b7a-155">Задание размера явным образом</span><span class="sxs-lookup"><span data-stu-id="26b7a-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="26b7a-156">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="26b7a-157">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-158"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент имеет значение 50 пикселей в ширину 70 пикселей в высоту, размер которой меньше, чем параметры макета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26b7a-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="26b7a-159">Содержимое [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления упорядочивается соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="26b7a-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="26b7a-160">Установка свойств макета</span><span class="sxs-lookup"><span data-stu-id="26b7a-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="26b7a-161">Всегда задавать свойства, связанные с макетом размещенного элемента управления, с помощью свойств <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="26b7a-162">При установке свойств макета непосредственно для размещаемого элемента управления результат не будет соответствовать ожидаемому.</span><span class="sxs-lookup"><span data-stu-id="26b7a-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="26b7a-163">Установка свойства, связанные с макетом размещенного элемента управления в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не делает ничего.</span><span class="sxs-lookup"><span data-stu-id="26b7a-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="26b7a-164">Чтобы увидеть влияние задания свойств размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="26b7a-165">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="26b7a-166">В обозревателе решений дважды щелкните файл MainWindow.xaml. vb</span><span class="sxs-lookup"><span data-stu-id="26b7a-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="26b7a-167">или MainWindow.xaml.cs, чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="26b7a-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="26b7a-168">Скопируйте следующий код в `MainWindow` определения класса.</span><span class="sxs-lookup"><span data-stu-id="26b7a-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="26b7a-169">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="26b7a-170">Нажмите кнопку **Click me** кнопки.</span><span class="sxs-lookup"><span data-stu-id="26b7a-170">Click the **Click me** button.</span></span> <span data-ttu-id="26b7a-171">`button1_Click` Задает обработчик событий <xref:System.Windows.Forms.Control.Top%2A> и <xref:System.Windows.Forms.Control.Left%2A> свойства размещенным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="26b7a-172">В результате размещенного элемента управления изменять внутри <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="26b7a-173">Ведущий элемент занимает то же пространство на экране, но размещаемый элемент управления обрезается.</span><span class="sxs-lookup"><span data-stu-id="26b7a-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="26b7a-174">Вместо этого размещаемый элемент управления должен всегда заполнять <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="26b7a-175">Описание ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="26b7a-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="26b7a-176">По умолчанию отображается <xref:System.Windows.Forms.Integration.WindowsFormsHost> элементы всегда рисуются поверх других [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы и они не подвержены влиянию z порядка.</span><span class="sxs-lookup"><span data-stu-id="26b7a-176">By default, visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="26b7a-177">Чтобы включить z порядка, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-177">To enable z-ordering, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-default-z-order-behavior"></a><span data-ttu-id="26b7a-178">Просмотр ограничений z-порядка</span><span class="sxs-lookup"><span data-stu-id="26b7a-178">To see the default z-order behavior</span></span>  
  
1.  <span data-ttu-id="26b7a-179">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-179">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  <span data-ttu-id="26b7a-180">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-180">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент рисуется через элемент label.</span><span class="sxs-lookup"><span data-stu-id="26b7a-181">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a><span data-ttu-id="26b7a-182">Чтобы увидеть поведение z порядка, когда свойству IsRedirected присвоено значение "true"</span><span class="sxs-lookup"><span data-stu-id="26b7a-182">To see the z-order behavior when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="26b7a-183">Замените следующий код XAML в предыдущем примере z порядка.</span><span class="sxs-lookup"><span data-stu-id="26b7a-183">Replace the previous z-order example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     <span data-ttu-id="26b7a-184">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-184">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-185">Элемент label рисуется через <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-185">The label element is painted over the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="docking"></a><span data-ttu-id="26b7a-186">Закрепление</span><span class="sxs-lookup"><span data-stu-id="26b7a-186">Docking</span></span>  
 <span data-ttu-id="26b7a-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>поддерживает элемент [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] закрепления.</span><span class="sxs-lookup"><span data-stu-id="26b7a-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="26b7a-188">Задать <xref:System.Windows.Controls.DockPanel.Dock%2A> вложенное свойство, чтобы закрепить размещенного элемента управления в <xref:System.Windows.Controls.DockPanel> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-188">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="26b7a-189">Закрепление размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-189">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="26b7a-190">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-190">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="26b7a-191">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-191">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-192"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент закреплен в правую часть <xref:System.Windows.Controls.DockPanel> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-192">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="26b7a-193">Задание видимости</span><span class="sxs-lookup"><span data-stu-id="26b7a-193">Setting Visibility</span></span>  
 <span data-ttu-id="26b7a-194">Можно сделать ваш [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления невидимым или свернуть его, задав <xref:System.Windows.UIElement.Visibility%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-194">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="26b7a-195">Если элемент управления невидим, он не отображается, но при этом занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="26b7a-195">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="26b7a-196">Если элемент управления свернут, он не отображается и не занимает пространство разметки.</span><span class="sxs-lookup"><span data-stu-id="26b7a-196">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="26b7a-197">Задание видимости размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-197">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="26b7a-198">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-198">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="26b7a-199">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="26b7a-199">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="26b7a-200">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-200">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="26b7a-201">Нажмите кнопку **щелкните, чтобы сделать невидимыми** кнопку, чтобы <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент невидимым.</span><span class="sxs-lookup"><span data-stu-id="26b7a-201">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="26b7a-202">Нажмите кнопку **щелкните, чтобы свернуть** кнопку, чтобы скрыть <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент из макета полностью.</span><span class="sxs-lookup"><span data-stu-id="26b7a-202">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="26b7a-203">Когда [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] управления свернут, соседние элементы переупорядочиваются, чтобы занять его место.</span><span class="sxs-lookup"><span data-stu-id="26b7a-203">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="26b7a-204">Размещение нерастягиваемых элементов управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-204">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="26b7a-205">Некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют фиксированный размер и не растягиваются для заполнения доступного места в макете.</span><span class="sxs-lookup"><span data-stu-id="26b7a-205">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="26b7a-206">Например <xref:System.Windows.Forms.MonthCalendar> элемент управления отображает месяц в фиксированное пространство.</span><span class="sxs-lookup"><span data-stu-id="26b7a-206">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="26b7a-207">Размещение нерастягиваемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-207">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="26b7a-208">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-208">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="26b7a-209">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-209">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-210"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемента выравнивается по центру в строке сетки, но она не растягивается для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="26b7a-210">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="26b7a-211">Если окно является достаточно большим, можно увидеть два или более месяцев, отображаемых размещаемым <xref:System.Windows.Forms.MonthCalendar> элемента управления, но они выравниваются по центру в строке.</span><span class="sxs-lookup"><span data-stu-id="26b7a-211">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="26b7a-212">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Обработчик макетов Центрирование элементов, которые не меняются для заполнения всего доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="26b7a-212">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="26b7a-213">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="26b7a-213">Scaling</span></span>  
 <span data-ttu-id="26b7a-214">В отличие от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, большинство [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления не являются непрерывно масштабируемыми.</span><span class="sxs-lookup"><span data-stu-id="26b7a-214">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, most [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls are not continuously scalable.</span></span> <span data-ttu-id="26b7a-215">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент масштабирует ее размещенного элемента управления, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="26b7a-215">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element scales its hosted control when possible.</span></span>  <span data-ttu-id="26b7a-216">Чтобы включить полноценные масштабирование, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-216">To enable full-fledged scaling, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="26b7a-217">Масштабирование размещаемого элемента управления с помощью поведения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="26b7a-217">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="26b7a-218">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-218">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="26b7a-219">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-219">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-220">Размещаемый элемент управления и его окружающие элементы масштабируются с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="26b7a-220">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="26b7a-221">Но шрифт размещаемого элемента управления не масштабируется.</span><span class="sxs-lookup"><span data-stu-id="26b7a-221">However, the hosted control's font is not scaled.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a><span data-ttu-id="26b7a-222">Масштабирование размещаемого элемента управления с помощью установки для свойства IsRedirected значения "true"</span><span class="sxs-lookup"><span data-stu-id="26b7a-222">To scale a hosted control by setting IsRedirected to true</span></span>  
  
1.  <span data-ttu-id="26b7a-223">Замените следующий код XAML в предыдущем примере масштабирования.</span><span class="sxs-lookup"><span data-stu-id="26b7a-223">Replace the previous scaling example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  <span data-ttu-id="26b7a-224">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-224">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-225">Шрифт размещаемого элемента управления, его окружающих элементов и вложенных в него элементов масштабируется с коэффициентом 0,5.</span><span class="sxs-lookup"><span data-stu-id="26b7a-225">The hosted control, its surrounding elements, and the hosted control's font are scaled by a factor of 0.5.</span></span>  
  
## <a name="rotating"></a><span data-ttu-id="26b7a-226">Поворот</span><span class="sxs-lookup"><span data-stu-id="26b7a-226">Rotating</span></span>  
 <span data-ttu-id="26b7a-227">В отличие от [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления не поддерживают поворот.</span><span class="sxs-lookup"><span data-stu-id="26b7a-227">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls do not support rotation.</span></span> <span data-ttu-id="26b7a-228">По умолчанию <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемент не поворачивается вместе с другими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы, когда применяется преобразование поворота.</span><span class="sxs-lookup"><span data-stu-id="26b7a-228">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements when a rotation transformation is applied.</span></span> <span data-ttu-id="26b7a-229">Значение поворота, отличное от 180 градусов, вызывает <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> событий.</span><span class="sxs-lookup"><span data-stu-id="26b7a-229">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>  <span data-ttu-id="26b7a-230">Чтобы включить на любой угол поворота, задайте <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost> значение true и <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> свойства <xref:System.Windows.Interop.CompositionMode.Full> или <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-230">To enable rotating to any angle, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="26b7a-231">Чтобы увидеть эффект от поворота в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="26b7a-231">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="26b7a-232">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-232">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="26b7a-233">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-233">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-234">Размещаемый элемент управления не повернут, но его соседние элементы повернуты на угол в 180 градусов.</span><span class="sxs-lookup"><span data-stu-id="26b7a-234">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="26b7a-235">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="26b7a-235">You may have to resize the window to see the elements.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a><span data-ttu-id="26b7a-236">Чтобы увидеть эффект от поворота в гибридном приложении, когда для свойства IsRedirected задано значение "true"</span><span class="sxs-lookup"><span data-stu-id="26b7a-236">To see the effect of rotation in a hybrid application when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="26b7a-237">Замените следующий код XAML в предыдущем примере поворота.</span><span class="sxs-lookup"><span data-stu-id="26b7a-237">Replace the previous rotation example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  <span data-ttu-id="26b7a-238">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-239">Размещаемый элемент повернут.</span><span class="sxs-lookup"><span data-stu-id="26b7a-239">The hosted control is rotated.</span></span>  <span data-ttu-id="26b7a-240">Обратите внимание, что <xref:System.Windows.Media.RotateTransform.Angle%2A> свойство может быть присвоено любое значение.</span><span class="sxs-lookup"><span data-stu-id="26b7a-240">Note that the <xref:System.Windows.Media.RotateTransform.Angle%2A> property can be set to any value.</span></span> <span data-ttu-id="26b7a-241">Для отображения элементов может потребоваться изменить размер окна.</span><span class="sxs-lookup"><span data-stu-id="26b7a-241">You may have to resize the window to see the elements.</span></span>  
  
## <a name="setting-padding-and-margins"></a><span data-ttu-id="26b7a-242">Задание отбивки и внутренних полей</span><span class="sxs-lookup"><span data-stu-id="26b7a-242">Setting Padding and Margins</span></span>  
 <span data-ttu-id="26b7a-243">Заполнение и поля в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макета аналогичны отступы и рамки, в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26b7a-243">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="26b7a-244">Просто установите <xref:System.Windows.Controls.Control.Padding%2A> и <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента.</span><span class="sxs-lookup"><span data-stu-id="26b7a-244">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="26b7a-245">Задание отбивки и внутренних полей размещаемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="26b7a-245">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="26b7a-246">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-246">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="26b7a-247">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-247">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-248">Параметры поля и заполнение применяются к размещаемым [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления таким же образом, как они будут применяться в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26b7a-248">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="26b7a-249">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="26b7a-249">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="26b7a-250">предусмотрены два типа контейнеров динамического макета, <xref:System.Windows.Forms.FlowLayoutPanel> и <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-250"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="26b7a-251">Можно также использовать эти контейнеры в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] макеты.</span><span class="sxs-lookup"><span data-stu-id="26b7a-251">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="26b7a-252">Использование динамических контейнеров макета</span><span class="sxs-lookup"><span data-stu-id="26b7a-252">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="26b7a-253">Скопируйте следующий код XAML в <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="26b7a-253">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="26b7a-254">В файле MainWindow.xaml.vb или MainWindow.xaml.cs скопируйте следующий код в определение класса.</span><span class="sxs-lookup"><span data-stu-id="26b7a-254">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="26b7a-255">Добавьте вызов `InitializeFlowLayoutPanel` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="26b7a-255">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="26b7a-256">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="26b7a-256">Press F5 to build and run the application.</span></span> <span data-ttu-id="26b7a-257"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Заполняет элемент <xref:System.Windows.Controls.DockPanel>, и <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает его дочерние элементы в значение по умолчанию <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="26b7a-257">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b7a-258">См. также</span><span class="sxs-lookup"><span data-stu-id="26b7a-258">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="26b7a-259">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="26b7a-259">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="26b7a-260">Вопросы, связанные с макетом элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="26b7a-260">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="26b7a-261">Элементы управления упорядочение Windows Forms в образце WPF</span><span class="sxs-lookup"><span data-stu-id="26b7a-261">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="26b7a-262">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="26b7a-262">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="26b7a-263">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26b7a-263">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
