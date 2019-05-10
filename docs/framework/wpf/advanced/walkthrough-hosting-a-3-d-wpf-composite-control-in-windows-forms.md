---
title: Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: 74f82f9be734cb7dc5225dc4226e14c2cee317df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605525"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="88cab-102">Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88cab-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="88cab-103">В этом пошаговом руководстве показано, как создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления и его размещения в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления и форм с помощью <xref:System.Windows.Forms.Integration.ElementHost> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88cab-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="88cab-104">В этом пошаговом руководстве будет реализовано [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , содержащий два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88cab-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="88cab-105"><xref:System.Windows.Controls.UserControl> Отображает трехмерного конуса (трехмерная).</span><span class="sxs-lookup"><span data-stu-id="88cab-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="88cab-106">Отрисовка трехмерных объектов стал гораздо проще благодаря [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] чем с [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cab-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="88cab-107">Таким образом, имеет смысл для размещения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> класса для создания трехмерной графики в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cab-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="88cab-108">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="88cab-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="88cab-109">Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="88cab-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="88cab-110">Создание ведущего проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88cab-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="88cab-111">Размещение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="88cab-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88cab-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="88cab-112">Prerequisites</span></span>

<span data-ttu-id="88cab-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="88cab-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="88cab-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="88cab-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="88cab-115">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="88cab-115">Create the UserControl</span></span>

1. <span data-ttu-id="88cab-116">Создание **Библиотека пользовательских элементов управления WPF** проект с именем `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="88cab-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="88cab-117">Откройте UserControl1.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="88cab-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="88cab-118">Замените сгенерированный код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="88cab-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="88cab-119">Этот код определяет <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , содержащий два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88cab-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="88cab-120">Первый дочерний элемент управления является <xref:System.Windows.Controls.Label?displayProperty=nameWithType> управления; второй — <xref:System.Windows.Controls.Viewport3D> элемент управления, отображающий трехмерного конуса.</span><span class="sxs-lookup"><span data-stu-id="88cab-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="88cab-121">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="88cab-121">Create the host project</span></span>

1. <span data-ttu-id="88cab-122">Добавить **приложение WPF (.NET Framework)** проект с именем `WpfUserControlHost` в решение.</span><span class="sxs-lookup"><span data-stu-id="88cab-122">Add a **WPF App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="88cab-123">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание первого классического приложения WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="88cab-123">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="88cab-124">В **обозревателе решений**, добавьте ссылку на сборку WindowsFormsIntegration с именем WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="88cab-124">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="88cab-125">Добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки:</span><span class="sxs-lookup"><span data-stu-id="88cab-125">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="88cab-126">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="88cab-126">PresentationCore</span></span>

    - <span data-ttu-id="88cab-127">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="88cab-127">PresentationFramework</span></span>

    - <span data-ttu-id="88cab-128">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="88cab-128">WindowsBase</span></span>

4. <span data-ttu-id="88cab-129">Добавьте ссылку на проект `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="88cab-129">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="88cab-130">В обозревателе решений задайте `WpfUserControlHost` как проект запуска.</span><span class="sxs-lookup"><span data-stu-id="88cab-130">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="88cab-131">Размещение пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="88cab-131">Host the UserControl</span></span>

1. <span data-ttu-id="88cab-132">В конструкторе Windows Forms откройте форму Form1.</span><span class="sxs-lookup"><span data-stu-id="88cab-132">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="88cab-133">В окне «Свойства» щелкните **события**, а затем дважды щелкните <xref:System.Windows.Forms.Form.Load> событие, чтобы создать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="88cab-133">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="88cab-134">Открывается редактор кода вновь созданным `Form1_Load` обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="88cab-134">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="88cab-135">Замените код в файле Form1.cs следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="88cab-135">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="88cab-136">`Form1_Load` Обработчик событий создает экземпляр класса `UserControl1` и добавляет изображением <xref:System.Windows.Forms.Integration.ElementHost> коллекцию дочерних элементов элемента управления.</span><span class="sxs-lookup"><span data-stu-id="88cab-136">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="88cab-137"><xref:System.Windows.Forms.Integration.ElementHost> Элемент управления добавляется в коллекцию дочерних элементов управления в формы.</span><span class="sxs-lookup"><span data-stu-id="88cab-137">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="88cab-138">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="88cab-138">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="88cab-139">См. также</span><span class="sxs-lookup"><span data-stu-id="88cab-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="88cab-140">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88cab-140">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="88cab-141">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88cab-141">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="88cab-142">Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF</span><span class="sxs-lookup"><span data-stu-id="88cab-142">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="88cab-143">Размещение составного элемента управления WPF в примере Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88cab-143">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)