---
title: Составной узел трехмерного элемента управления WPF в Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: aaa726ac90fd75a12054c18be6ec08a1372c1128
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794211"
---
# <a name="walkthrough-host-a-3d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="608d5-102">Пошаговое руководство. размещение составного трехмерного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="608d5-102">Walkthrough: Host a 3D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="608d5-103">В этом пошаговом руководстве показано, как можно создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составной элемент управления и разместить его в Windows Forms элементах управления и формах с помощью элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="608d5-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in Windows Forms controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="608d5-104">В этом пошаговом руководстве будет реализована [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>, содержащая два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="608d5-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="608d5-105"><xref:System.Windows.Controls.UserControl> отображает трехмерный (трехмерный) конус.</span><span class="sxs-lookup"><span data-stu-id="608d5-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3D) cone.</span></span> <span data-ttu-id="608d5-106">Отрисовка трехмерных объектов гораздо проще с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], чем с помощью Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="608d5-106">Rendering 3D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with Windows Forms.</span></span> <span data-ttu-id="608d5-107">Поэтому имеет смысл разместить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> класса для создания трехмерной графики в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="608d5-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3D graphics in Windows Forms.</span></span>

<span data-ttu-id="608d5-108">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="608d5-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="608d5-109">Создание <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="608d5-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="608d5-110">Создание проекта Windows Forms узла.</span><span class="sxs-lookup"><span data-stu-id="608d5-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="608d5-111">Размещение <xref:System.Windows.Controls.UserControl>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="608d5-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="608d5-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="608d5-112">Prerequisites</span></span>

<span data-ttu-id="608d5-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="608d5-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="608d5-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="608d5-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="608d5-115">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="608d5-115">Create the UserControl</span></span>

1. <span data-ttu-id="608d5-116">Создайте проект **библиотеки пользовательских элементов управления WPF** с именем `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="608d5-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="608d5-117">Откройте UserControl1. XAML в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="608d5-117">Open UserControl1.xaml in the WPF Designer.</span></span>

3. <span data-ttu-id="608d5-118">Замените созданный код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="608d5-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="608d5-119">Этот код определяет <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>, содержащий два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="608d5-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="608d5-120">Первый дочерний элемент управления является <xref:System.Windows.Controls.Label?displayProperty=nameWithType> элементом управления; второй — элемент управления <xref:System.Windows.Controls.Viewport3D>, отображающий трехмерную конус.</span><span class="sxs-lookup"><span data-stu-id="608d5-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="608d5-121">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="608d5-121">Create the host project</span></span>

1. <span data-ttu-id="608d5-122">Добавьте в решение проект **Windows Formsного приложения (.NET Framework)** с именем `WpfUserControlHost`.</span><span class="sxs-lookup"><span data-stu-id="608d5-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="608d5-123">В **Обозреватель решений**добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="608d5-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="608d5-124">Добавьте ссылки на следующие сборки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="608d5-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="608d5-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="608d5-125">PresentationCore</span></span>

    - <span data-ttu-id="608d5-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="608d5-126">PresentationFramework</span></span>

    - <span data-ttu-id="608d5-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="608d5-127">WindowsBase</span></span>

4. <span data-ttu-id="608d5-128">Добавьте ссылку на проект `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="608d5-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="608d5-129">В обозреватель решений установите проект `WpfUserControlHost` в качестве запускаемого проекта.</span><span class="sxs-lookup"><span data-stu-id="608d5-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="608d5-130">Размещение пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="608d5-130">Host the UserControl</span></span>

1. <span data-ttu-id="608d5-131">В конструктор Windows Forms откройте форму Form1.</span><span class="sxs-lookup"><span data-stu-id="608d5-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="608d5-132">В окно свойств щелкните **события**, а затем дважды щелкните событие <xref:System.Windows.Forms.Form.Load>, чтобы создать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="608d5-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="608d5-133">Редактор кода открывает только что созданный обработчик событий `Form1_Load`.</span><span class="sxs-lookup"><span data-stu-id="608d5-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="608d5-134">Замените код в Form1.cs на следующий код.</span><span class="sxs-lookup"><span data-stu-id="608d5-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="608d5-135">Обработчик событий `Form1_Load` создает экземпляр `UserControl1` и добавляет Итто коллекцию дочерних элементов управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="608d5-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="608d5-136">Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> добавляется в коллекцию формы дочерних элементов управления.</span><span class="sxs-lookup"><span data-stu-id="608d5-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="608d5-137">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="608d5-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="608d5-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="608d5-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="608d5-139">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="608d5-139">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="608d5-140">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="608d5-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="608d5-141">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="608d5-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="608d5-142">Размещение составного элемента управления WPF в Windows Forms примере</span><span class="sxs-lookup"><span data-stu-id="608d5-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
