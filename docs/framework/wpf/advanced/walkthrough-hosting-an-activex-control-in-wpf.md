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
ms.openlocfilehash: 395081640815f00ce4ae8e83f25b37de567adc01
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920199"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="49c50-102">Пошаговое руководство. Размещение элемента управления ActiveX в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="49c50-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="49c50-103">Чтобы обеспечить улучшенное взаимодействие с браузерами, можно использовать элементы управления Microsoft ActiveX в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49c50-103">To enable improved interaction with browsers, you can use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="49c50-104">В этом пошаговом руководстве показано, как можно разместить [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] как элемент управления на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] странице.</span><span class="sxs-lookup"><span data-stu-id="49c50-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>

 <span data-ttu-id="49c50-105">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="49c50-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="49c50-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="49c50-106">Creating the project.</span></span>

- <span data-ttu-id="49c50-107">Создание элемента управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="49c50-107">Creating the ActiveX control.</span></span>

- <span data-ttu-id="49c50-108">Размещение элемента управления ActiveX на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="49c50-108">Hosting the ActiveX control on a WPF Page.</span></span>

 <span data-ttu-id="49c50-109">После завершения этого пошагового руководства вы узнаете, как использовать элементы управления Microsoft ActiveX в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49c50-109">When you have completed this walkthrough, you will understand how to use Microsoft ActiveX controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49c50-110">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="49c50-110">Prerequisites</span></span>
 <span data-ttu-id="49c50-111">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="49c50-111">You need the following components to complete this walkthrough:</span></span>

- [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]<span data-ttu-id="49c50-112">, установленные на компьютере, где установлена система Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49c50-112">installed on the computer where Visual Studio is installed.</span></span>

- <span data-ttu-id="49c50-113">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="49c50-113">Visual Studio 2010.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="49c50-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="49c50-114">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="49c50-115">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="49c50-115">To create and set up the project</span></span>

1. <span data-ttu-id="49c50-116">Создайте проект приложения WPF с именем `HostingAxInWpf`.</span><span class="sxs-lookup"><span data-stu-id="49c50-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>

2. <span data-ttu-id="49c50-117">Добавьте в решение проект библиотеки элементов управления Windows Forms и присвойте проекту имя `WmpAxLib`.</span><span class="sxs-lookup"><span data-stu-id="49c50-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>

3. <span data-ttu-id="49c50-118">В проекте Вмпакслиб добавьте ссылку на сборку проигрывателя Windows Media, которая называется WMP. dll.</span><span class="sxs-lookup"><span data-stu-id="49c50-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>

4. <span data-ttu-id="49c50-119">Откройте **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="49c50-119">Open the **Toolbox**.</span></span>

5. <span data-ttu-id="49c50-120">Щелкните правой кнопкой мыши **область элементов**и выберите пункт **выбрать элементы**.</span><span class="sxs-lookup"><span data-stu-id="49c50-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>

6. <span data-ttu-id="49c50-121">Перейдите на вкладку **COM-компоненты** , выберите элемент управления **проигрывателя Windows Media** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49c50-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>

     <span data-ttu-id="49c50-122">Элемент управления проигрывателя Windows Media добавляется на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="49c50-122">The Windows Media Player control is added to the **Toolbox**.</span></span>

7. <span data-ttu-id="49c50-123">В обозреватель решений щелкните правой кнопкой мыши файл **UserControl1** и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="49c50-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>

8. <span data-ttu-id="49c50-124">Измените имя на `WmpAxControl.vb` или `WmpAxControl.cs`в зависимости от языка.</span><span class="sxs-lookup"><span data-stu-id="49c50-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>

9. <span data-ttu-id="49c50-125">Если появится запрос на переименование всех ссылок, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="49c50-125">If you are prompted to rename all references, click **Yes**.</span></span>

## <a name="creating-the-activex-control"></a><span data-ttu-id="49c50-126">Создание элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="49c50-126">Creating the ActiveX Control</span></span>
<span data-ttu-id="49c50-127">Visual Studio автоматически создает класс-оболочку <xref:System.Windows.Forms.AxHost> для элемента управления Microsoft ActiveX, когда элемент управления добавляется в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="49c50-127">Visual Studio automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a Microsoft ActiveX control when the control is added to a design surface.</span></span> <span data-ttu-id="49c50-128">Следующая процедура создает управляемую сборку с именем Аксинтероп. Вмплиб. dll.</span><span class="sxs-lookup"><span data-stu-id="49c50-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>

### <a name="to-create-the-activex-control"></a><span data-ttu-id="49c50-129">Создание элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="49c50-129">To create the ActiveX control</span></span>

1. <span data-ttu-id="49c50-130">Откройте Вмпаксконтрол. vb или WmpAxControl.cs в конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="49c50-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="49c50-131">Из **панели элементов**добавьте элемент управления проигрывателя Windows Media в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="49c50-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>

3. <span data-ttu-id="49c50-132">В окно свойств задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> элемента управления проигрывателя Windows Media значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="49c50-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

4. <span data-ttu-id="49c50-133">Создайте проект библиотеки элементов управления Вмпакслиб.</span><span class="sxs-lookup"><span data-stu-id="49c50-133">Build the WmpAxLib control library project.</span></span>

## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="49c50-134">Размещение элемента управления ActiveX на странице WPF</span><span class="sxs-lookup"><span data-stu-id="49c50-134">Hosting the ActiveX Control on a WPF Page</span></span>

### <a name="to-host-the-activex-control"></a><span data-ttu-id="49c50-135">Размещение элемента управления ActiveX</span><span class="sxs-lookup"><span data-stu-id="49c50-135">To host the ActiveX control</span></span>

1. <span data-ttu-id="49c50-136">В проекте Хостингаксинвпф добавьте ссылку на созданную сборку взаимодействия ActiveX.</span><span class="sxs-lookup"><span data-stu-id="49c50-136">In the HostingAxInWpf project, add a reference to the generated ActiveX interoperability assembly.</span></span>

     <span data-ttu-id="49c50-137">Эта сборка называется Аксинтероп. Вмплиб. dll и была добавлена в папку Debug проекта Вмпакслиб при импорте элемента управления проигрывателя Windows Media.</span><span class="sxs-lookup"><span data-stu-id="49c50-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>

2. <span data-ttu-id="49c50-138">Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="49c50-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="49c50-139">Добавьте ссылку на сборку [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], которая называется System. Windows. Forms. dll.</span><span class="sxs-lookup"><span data-stu-id="49c50-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>

4. <span data-ttu-id="49c50-140">Откройте файл MainWindow. XAML в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="49c50-140">Open MainWindow.xaml in the WPF Designer.</span></span>

5. <span data-ttu-id="49c50-141">Назовите `grid1`элемент <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="49c50-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. <span data-ttu-id="49c50-142">В представление конструирования или представлении XAML выберите элемент <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="49c50-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

7. <span data-ttu-id="49c50-143">В окно свойств перейдите на вкладку **события** .</span><span class="sxs-lookup"><span data-stu-id="49c50-143">In the Properties window, click the **Events** tab.</span></span>

8. <span data-ttu-id="49c50-144">Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="49c50-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

9. <span data-ttu-id="49c50-145">Вставьте следующий код, обрабатывающий событие <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="49c50-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     <span data-ttu-id="49c50-146">Этот код создает экземпляр элемента управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> и добавляет экземпляр элемента управления `AxWindowsMediaPlayer` в качестве дочернего.</span><span class="sxs-lookup"><span data-stu-id="49c50-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="49c50-147">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="49c50-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c50-148">См. также</span><span class="sxs-lookup"><span data-stu-id="49c50-148">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="49c50-149">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="49c50-149">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="49c50-150">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="49c50-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="49c50-151">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49c50-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
