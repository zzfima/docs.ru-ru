---
title: Пошаговое руководство. Размещение элемента управления ActiveX в WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 25019444e107af2ad681e9f51adebbf01c444438
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668324"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="25eee-102">Пошаговое руководство. Размещение элемента управления ActiveX в WPF</span><span class="sxs-lookup"><span data-stu-id="25eee-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="25eee-103">Для улучшенного взаимодействия с браузерами, можно использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="25eee-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="25eee-104">В этом пошаговом руководстве показано, как разместить [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] как элемент управления на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="25eee-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="25eee-105">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="25eee-105">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="25eee-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="25eee-106">Creating the project.</span></span>

-   <span data-ttu-id="25eee-107">Создание элемента управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="25eee-107">Creating the ActiveX control.</span></span>

-   <span data-ttu-id="25eee-108">Размещение элемента управления ActiveX на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="25eee-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="25eee-109">После завершения этого пошагового руководства вы узнаете, как использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="25eee-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25eee-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="25eee-110">Prerequisites</span></span>
 <span data-ttu-id="25eee-111">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="25eee-111">You need the following components to complete this walkthrough:</span></span>

-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] <span data-ttu-id="25eee-112">установлена на компьютере, где установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="25eee-112">installed on the computer where Visual Studio is installed.</span></span>

-   <span data-ttu-id="25eee-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="25eee-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="25eee-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="25eee-114">Creating the Project</span></span>

#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="25eee-115">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="25eee-115">To create and set up the project</span></span>

1.  <span data-ttu-id="25eee-116">Создание проекта приложения WPF с именем `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="25eee-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2.  <span data-ttu-id="25eee-117">Добавить в решение проекта библиотеки элементов управления Windows Forms и назовите проект `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="25eee-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3.  <span data-ttu-id="25eee-118">В проекте WmpAxLib добавьте ссылку на сборку проигрывателя Windows Media, которая называется wmp.dll.</span><span class="sxs-lookup"><span data-stu-id="25eee-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4.  <span data-ttu-id="25eee-119">Откройте **элементов**.</span><span class="sxs-lookup"><span data-stu-id="25eee-119">Open the **Toolbox**.</span></span>

5.  <span data-ttu-id="25eee-120">Щелкните правой кнопкой мыши в **элементов**, а затем нажмите кнопку **Выбор элементов**.</span><span class="sxs-lookup"><span data-stu-id="25eee-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6.  <span data-ttu-id="25eee-121">Нажмите кнопку **COM-компоненты** выберите **проигрывателя Windows Media** управления, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="25eee-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="25eee-122">Добавляемый элемент управления проигрывателя Windows Media **элементов**.</span><span class="sxs-lookup"><span data-stu-id="25eee-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7.  <span data-ttu-id="25eee-123">В обозревателе решений щелкните правой кнопкой мыши **UserControl1** файла и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="25eee-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8.  <span data-ttu-id="25eee-124">Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`в зависимости от языка.</span><span class="sxs-lookup"><span data-stu-id="25eee-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="25eee-125">Если в ответ на приглашение переименовать все ссылки, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="25eee-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="25eee-126">Создание элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="25eee-126">Creating the ActiveX Control</span></span>
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <span data-ttu-id="25eee-127">автоматически создает <xref:System.Windows.Forms.AxHost> класс-оболочку для [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] управления, когда элемент управления добавляется в рабочую область конструирования.</span><span class="sxs-lookup"><span data-stu-id="25eee-127">automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="25eee-128">В следующей процедуре создается управляемая сборка с именем AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="25eee-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

#### <a name="to-create-the-activex-control"></a><span data-ttu-id="25eee-129">Чтобы создать элемент управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="25eee-129">To create the ActiveX control</span></span>

1.  <span data-ttu-id="25eee-130">Откройте WmpAxControl.vb или WmpAxControl.cs в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="25eee-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2.  <span data-ttu-id="25eee-131">Из **элементов**, добавьте элемент управления проигрывателя Windows Media в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="25eee-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3.  <span data-ttu-id="25eee-132">В окне свойств установите для параметра элемента управления проигрывателя Windows Media <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="25eee-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4.  <span data-ttu-id="25eee-133">Создание проекта библиотеки элементов управления WmpAxLib.</span><span class="sxs-lookup"><span data-stu-id="25eee-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="25eee-134">Размещение элемента управления ActiveX в страницу WPF</span><span class="sxs-lookup"><span data-stu-id="25eee-134">Hosting the ActiveX Control on a WPF Page</span></span>

#### <a name="to-host-the-activex-control"></a><span data-ttu-id="25eee-135">Размещение элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="25eee-135">To host the ActiveX control</span></span>

1.  <span data-ttu-id="25eee-136">В проекте HostingAxInWpf, добавьте ссылку на созданный [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] сборка взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="25eee-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>

     <span data-ttu-id="25eee-137">Эта сборка называется AxInterop.WMPLib.dll и был добавлен в папку отладки проекта WmpAxLib при импорте элементом управления проигрывателя Windows Media.</span><span class="sxs-lookup"><span data-stu-id="25eee-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2.  <span data-ttu-id="25eee-138">Добавьте ссылку на сборку WindowsFormsIntegration с именем WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="25eee-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3.  <span data-ttu-id="25eee-139">Добавьте ссылку на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сборку, которая называется System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="25eee-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4.  <span data-ttu-id="25eee-140">Откройте файл MainWindow.xaml в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="25eee-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5.  <span data-ttu-id="25eee-141">Имя <xref:System.Windows.Controls.Grid> элемент `grid1`.</span><span class="sxs-lookup"><span data-stu-id="25eee-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6.  <span data-ttu-id="25eee-142">В представлении конструирования или XAML, выберите <xref:System.Windows.Window> элемент.</span><span class="sxs-lookup"><span data-stu-id="25eee-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7.  <span data-ttu-id="25eee-143">В окне «Свойства» щелкните **события** вкладки.</span><span class="sxs-lookup"><span data-stu-id="25eee-143">In the Properties window, click the **Events** tab.</span></span>

8.  <span data-ttu-id="25eee-144">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="25eee-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="25eee-145">Вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="25eee-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="25eee-146">Этот код создает экземпляр класса <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления и добавляет экземпляр `AxWindowsMediaPlayer` элемента управления в качестве дочернего.</span><span class="sxs-lookup"><span data-stu-id="25eee-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="25eee-147">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="25eee-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25eee-148">См. также</span><span class="sxs-lookup"><span data-stu-id="25eee-148">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="25eee-149">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25eee-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="25eee-150">Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF</span><span class="sxs-lookup"><span data-stu-id="25eee-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="25eee-151">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25eee-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
