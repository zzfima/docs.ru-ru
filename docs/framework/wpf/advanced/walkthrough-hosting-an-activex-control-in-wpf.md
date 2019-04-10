---
title: Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: c27449da5ee0351e472eaba7d930a774979db65f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311505"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="bc87b-102">Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="bc87b-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="bc87b-103">Для улучшенного взаимодействия с браузерами, можно использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="bc87b-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="bc87b-104">В этом пошаговом руководстве показано, как разместить [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] как элемент управления на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы.</span><span class="sxs-lookup"><span data-stu-id="bc87b-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="bc87b-105">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="bc87b-105">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="bc87b-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="bc87b-106">Creating the project.</span></span>

-   <span data-ttu-id="bc87b-107">Создание элемента управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="bc87b-107">Creating the ActiveX control.</span></span>

-   <span data-ttu-id="bc87b-108">Размещение элемента управления ActiveX на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="bc87b-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="bc87b-109">После завершения этого пошагового руководства вы узнаете, как использовать [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="bc87b-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc87b-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bc87b-110">Prerequisites</span></span>
 <span data-ttu-id="bc87b-111">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="bc87b-111">You need the following components to complete this walkthrough:</span></span>

-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] <span data-ttu-id="bc87b-112">установлена на компьютере, где установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc87b-112">installed on the computer where Visual Studio is installed.</span></span>

-   <span data-ttu-id="bc87b-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="bc87b-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="bc87b-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="bc87b-114">Creating the Project</span></span>

#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="bc87b-115">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="bc87b-115">To create and set up the project</span></span>

1. <span data-ttu-id="bc87b-116">Создание проекта приложения WPF с именем `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="bc87b-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="bc87b-117">Добавить в решение проекта библиотеки элементов управления Windows Forms и назовите проект `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="bc87b-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="bc87b-118">В проекте WmpAxLib добавьте ссылку на сборку проигрывателя Windows Media, которая называется wmp.dll.</span><span class="sxs-lookup"><span data-stu-id="bc87b-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="bc87b-119">Откройте **элементов**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="bc87b-120">Щелкните правой кнопкой мыши в **элементов**, а затем нажмите кнопку **Выбор элементов**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="bc87b-121">Нажмите кнопку **COM-компоненты** выберите **проигрывателя Windows Media** управления, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="bc87b-122">Добавляемый элемент управления проигрывателя Windows Media **элементов**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="bc87b-123">В обозревателе решений щелкните правой кнопкой мыши **UserControl1** файла и нажмите кнопку **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="bc87b-124">Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`в зависимости от языка.</span><span class="sxs-lookup"><span data-stu-id="bc87b-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="bc87b-125">Если в ответ на приглашение переименовать все ссылки, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="bc87b-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="bc87b-126">Создание элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="bc87b-126">Creating the ActiveX Control</span></span>
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <span data-ttu-id="bc87b-127">автоматически создает <xref:System.Windows.Forms.AxHost> класс-оболочку для [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] управления, когда элемент управления добавляется в рабочую область конструирования.</span><span class="sxs-lookup"><span data-stu-id="bc87b-127">automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="bc87b-128">В следующей процедуре создается управляемая сборка с именем AxInterop.WMPLib.dll.</span><span class="sxs-lookup"><span data-stu-id="bc87b-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

#### <a name="to-create-the-activex-control"></a><span data-ttu-id="bc87b-129">Чтобы создать элемент управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="bc87b-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="bc87b-130">Откройте WmpAxControl.vb или WmpAxControl.cs в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bc87b-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="bc87b-131">Из **элементов**, добавьте элемент управления проигрывателя Windows Media в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="bc87b-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="bc87b-132">В окне свойств установите для параметра элемента управления проигрывателя Windows Media <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="bc87b-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="bc87b-133">Создание проекта библиотеки элементов управления WmpAxLib.</span><span class="sxs-lookup"><span data-stu-id="bc87b-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="bc87b-134">Размещение элемента управления ActiveX в страницу WPF</span><span class="sxs-lookup"><span data-stu-id="bc87b-134">Hosting the ActiveX Control on a WPF Page</span></span>

#### <a name="to-host-the-activex-control"></a><span data-ttu-id="bc87b-135">Размещение элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="bc87b-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="bc87b-136">В проекте HostingAxInWpf, добавьте ссылку на созданный [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] сборка взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="bc87b-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>

     <span data-ttu-id="bc87b-137">Эта сборка называется AxInterop.WMPLib.dll и был добавлен в папку отладки проекта WmpAxLib при импорте элементом управления проигрывателя Windows Media.</span><span class="sxs-lookup"><span data-stu-id="bc87b-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="bc87b-138">Добавьте ссылку на сборку WindowsFormsIntegration с именем WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="bc87b-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="bc87b-139">Добавьте ссылку на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] сборку, которая называется System.Windows.Forms.dll.</span><span class="sxs-lookup"><span data-stu-id="bc87b-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="bc87b-140">Откройте файл MainWindow.xaml в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="bc87b-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="bc87b-141">Имя <xref:System.Windows.Controls.Grid> элемент `grid1`.</span><span class="sxs-lookup"><span data-stu-id="bc87b-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="bc87b-142">В представлении конструирования или XAML, выберите <xref:System.Windows.Window> элемент.</span><span class="sxs-lookup"><span data-stu-id="bc87b-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="bc87b-143">В окне «Свойства» щелкните **события** вкладки.</span><span class="sxs-lookup"><span data-stu-id="bc87b-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="bc87b-144">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="bc87b-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="bc87b-145">Вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="bc87b-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="bc87b-146">Этот код создает экземпляр класса <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления и добавляет экземпляр `AxWindowsMediaPlayer` элемента управления в качестве дочернего.</span><span class="sxs-lookup"><span data-stu-id="bc87b-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="bc87b-147">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="bc87b-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc87b-148">См. также</span><span class="sxs-lookup"><span data-stu-id="bc87b-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="bc87b-149">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bc87b-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="bc87b-150">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="bc87b-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="bc87b-151">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc87b-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
