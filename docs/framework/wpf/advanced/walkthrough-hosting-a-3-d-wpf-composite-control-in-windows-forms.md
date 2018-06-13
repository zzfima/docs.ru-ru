---
title: Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a9aca5d1aff1057d85509be517bb352b4b27bf9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548211"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="c0cd4-102">Пошаговое руководство. Размещение составного трехмерного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0cd4-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>
<span data-ttu-id="c0cd4-103">В этом пошаговом руководстве показано, как можно создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] составного элемента управления и его размещения в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления и форм с помощью <xref:System.Windows.Forms.Integration.ElementHost> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
 <span data-ttu-id="c0cd4-104">В этом пошаговом руководстве будет реализовывать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , содержащий два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="c0cd4-105"><xref:System.Windows.Controls.UserControl> Отображает трехмерного конуса (трехмерные).</span><span class="sxs-lookup"><span data-stu-id="c0cd4-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="c0cd4-106">Подготовка к просмотру трехмерных объектов теперь гораздо проще с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] чем с [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0cd4-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="c0cd4-107">Таким образом, имеет смысл узел [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> класс для создания трехмерной графики в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0cd4-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="c0cd4-108">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="c0cd4-109">Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
-   <span data-ttu-id="c0cd4-110">Создание базового проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-110">Creating the Windows Forms host project.</span></span>  
  
-   <span data-ttu-id="c0cd4-111">Размещение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>  
  
 <span data-ttu-id="c0cd4-112">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [размещение трехмерных составного элемента управления WPF в Windows Forms образец](http://go.microsoft.com/fwlink/?LinkID=160001).</span><span class="sxs-lookup"><span data-stu-id="c0cd4-112">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a 3-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c0cd4-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c0cd4-113">Prerequisites</span></span>  
 <span data-ttu-id="c0cd4-114">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="c0cd4-115">.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-115">.</span></span>  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a><span data-ttu-id="c0cd4-116">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="c0cd4-116">Creating the UserControl</span></span>  
  
#### <a name="to-create-the-usercontrol"></a><span data-ttu-id="c0cd4-117">Для создания пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="c0cd4-117">To create the UserControl</span></span>  
  
1.  <span data-ttu-id="c0cd4-118">Создайте проект библиотеки пользовательских элементов управления WPF с именем `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-118">Create a WPF User Control Library project named `HostingWpfUserControlInWf`.</span></span>  
  
2.  <span data-ttu-id="c0cd4-119">Откройте UserControl1.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0cd4-119">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
3.  <span data-ttu-id="c0cd4-120">Замените созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-120">Replace the generated code with the following code.</span></span>  
  
     <span data-ttu-id="c0cd4-121">Этот код определяет <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , содержащий два дочерних элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-121">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="c0cd4-122">Первый дочерний элемент управления является <xref:System.Windows.Controls.Label?displayProperty=nameWithType> управления; второй — <xref:System.Windows.Controls.Viewport3D> элемент управления, отображающий объемный вариант.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-122">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="c0cd4-123">Создание ведущего проекта Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0cd4-123">Creating the Windows Forms Host Project</span></span>  
  
#### <a name="to-create-the-host-project"></a><span data-ttu-id="c0cd4-124">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="c0cd4-124">To create the host project</span></span>  
  
1.  <span data-ttu-id="c0cd4-125">Добавьте проект приложения Windows с именем `WpfUserControlHost` в решение.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-125">Add a Windows application project named `WpfUserControlHost` to the solution.</span></span> <span data-ttu-id="c0cd4-126">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="c0cd4-126">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="c0cd4-127">В обозревателе решений добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-127">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="c0cd4-128">Добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки:</span><span class="sxs-lookup"><span data-stu-id="c0cd4-128">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>  
  
    -   <span data-ttu-id="c0cd4-129">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="c0cd4-129">PresentationCore</span></span>  
  
    -   <span data-ttu-id="c0cd4-130">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="c0cd4-130">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="c0cd4-131">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="c0cd4-131">WindowsBase</span></span>  
  
4.  <span data-ttu-id="c0cd4-132">Добавьте ссылку на проект `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-132">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>  
  
5.  <span data-ttu-id="c0cd4-133">В обозревателе решений задайте `WpfUserControlHost` как проект запуска.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-133">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a><span data-ttu-id="c0cd4-134">Размещение пользовательского элемента управления Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="c0cd4-134">Hosting the Windows Presentation Foundation UserControl</span></span>  
  
#### <a name="to-host-the-usercontrol"></a><span data-ttu-id="c0cd4-135">Размещение пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="c0cd4-135">To host the UserControl</span></span>  
  
1.  <span data-ttu-id="c0cd4-136">Откройте форму Form1 в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-136">In the Windows Forms Designer, open Form1.</span></span>  
  
2.  <span data-ttu-id="c0cd4-137">В окне «Свойства» щелкните **событий**, а затем дважды щелкните <xref:System.Windows.Forms.Form.Load> событие, чтобы создать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-137">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>  
  
     <span data-ttu-id="c0cd4-138">Открывается редактор кода в только что созданный `Form1_Load` обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-138">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>  
  
3.  <span data-ttu-id="c0cd4-139">Замените код в файле Form1.cs следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-139">Replace the code in Form1.cs with the following code.</span></span>  
  
     <span data-ttu-id="c0cd4-140">`Form1_Load` Обработчик событий создает экземпляр `UserControl1` и добавляет itto <xref:System.Windows.Forms.Integration.ElementHost> коллекцию дочерних элементов управления элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-140">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="c0cd4-141"><xref:System.Windows.Forms.Integration.ElementHost> Элемент управления добавляется в коллекцию дочерних элементов управления формы.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-141">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="c0cd4-142">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="c0cd4-142">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0cd4-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c0cd4-143">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c0cd4-144">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="c0cd4-144">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="c0cd4-145">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0cd4-145">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="c0cd4-146">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="c0cd4-146">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="c0cd4-147">Размещение составного элемента управления WPF в Windows Forms образца</span><span class="sxs-lookup"><span data-stu-id="c0cd4-147">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160001)
