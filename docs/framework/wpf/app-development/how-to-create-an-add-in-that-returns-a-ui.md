---
title: Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 1886703e089ed538f68a7221906d815a8ae72076
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182672"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="0cbcd-102">Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="0cbcd-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="0cbcd-103">В этом примере показано, как создать надстройку, которая возвращает Windows Presentation Foundation (WPF) в изолированное приложение WPF узла.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="0cbcd-104">Надстройка возвращает пользовательский интерфейс, который является пользовательским элементом управления WPF.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="0cbcd-105">Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="0cbcd-106">Автономное приложение WPF размещает надстройку и отображает пользовательский элемент управления (возвращаемый надстройкой) в качестве содержимого главного окна приложения.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="0cbcd-107">**Необходимые компоненты**</span><span class="sxs-lookup"><span data-stu-id="0cbcd-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="0cbcd-108">В этом примере расширения WPF выделены для модели надстройки .NET Framework, которая включает этот сценарий и предполагает следующее:</span><span class="sxs-lookup"><span data-stu-id="0cbcd-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="0cbcd-109">Знание модели надстроек .NET Framework, включая конвейер, надстройку и разработку на узле.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="0cbcd-110">Если вы не знакомы с этими понятиями, см. раздел [надстройки и расширяемость](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span><span class="sxs-lookup"><span data-stu-id="0cbcd-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="0cbcd-111">Руководство, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, см. в разделе [пошаговое руководство. Создание расширяемого приложения](../../add-ins/walkthrough-create-extensible-app.md).</span><span class="sxs-lookup"><span data-stu-id="0cbcd-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
- <span data-ttu-id="0cbcd-112">Сведения о расширениях WPF для модели надстроек .NET Framework, которые можно найти здесь: [Общие сведения о](wpf-add-ins-overview.md)надстройках WPF.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cbcd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="0cbcd-113">Example</span></span>  
 <span data-ttu-id="0cbcd-114">Чтобы создать надстройку, которая возвращает пользовательский интерфейс WPF, требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="0cbcd-115">Реализация сегмента конвейера контракта</span><span class="sxs-lookup"><span data-stu-id="0cbcd-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="0cbcd-116">Метод должен быть определен контрактом для возврата пользовательского интерфейса, и его возвращаемое значение должно иметь тип <xref:System.AddIn.Contract.INativeHandleContract>.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="0cbcd-117">Это продемонстрировано `GetAddInUI` в методе `IWPFAddInContract` контракта в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="0cbcd-118">Реализация сегмента конвейера представления надстройки</span><span class="sxs-lookup"><span data-stu-id="0cbcd-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="0cbcd-119">Так как надстройка реализует, она [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] предоставляет в качестве подклассов <xref:System.Windows.FrameworkElement>, метод в `IWPFAddInView.GetAddInUI` представлении надстройки, соответствующий, должен возвращать значение типа <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="0cbcd-120">В следующем коде показано представление надстройки контракта, реализованное как интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="0cbcd-121">Реализация сегмента конвейера адаптера надстройки</span><span class="sxs-lookup"><span data-stu-id="0cbcd-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="0cbcd-122">Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но надстройка возвращает значение <xref:System.Windows.FrameworkElement> (как указано в представлении надстройки).</span><span class="sxs-lookup"><span data-stu-id="0cbcd-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="0cbcd-123">Следовательно, <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Contract.INativeHandleContract> перед пересечением границы изоляции необходимо преобразовать в.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="0cbcd-124">Эта работа выполняется с помощью адаптера надстройки путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="0cbcd-125">Реализация сегмента конвейера представления в основном приложении</span><span class="sxs-lookup"><span data-stu-id="0cbcd-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="0cbcd-126">Так как ведущее приложение будет отображать <xref:System.Windows.FrameworkElement>, метод в представлении узла, `IWPFAddInHostView.GetAddInUI` соответствующий, должен возвращать значение типа <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="0cbcd-127">В следующем коде показано представление контракта в основном приложении, реализованное как интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="0cbcd-128">Реализация сегмента конвейера адаптера приложения</span><span class="sxs-lookup"><span data-stu-id="0cbcd-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="0cbcd-129">Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но ведущее приложение принимает значение <xref:System.Windows.FrameworkElement> (как указано представлением главного приложения).</span><span class="sxs-lookup"><span data-stu-id="0cbcd-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="0cbcd-130">Следовательно, <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> после пересечения границы изоляции необходимо преобразовать в.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="0cbcd-131">Эта работа выполняется адаптером на стороне главного приложения путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="0cbcd-132">Реализация надстройки</span><span class="sxs-lookup"><span data-stu-id="0cbcd-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="0cbcd-133">После создания адаптера надстройки и представления`WPFAddIn1.AddIn`надстройки Надстройка () должна `IWPFAddInView.GetAddInUI` реализовать метод для возврата <xref:System.Windows.FrameworkElement> объекта (в этом примере — <xref:System.Windows.Controls.UserControl> ).</span><span class="sxs-lookup"><span data-stu-id="0cbcd-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="0cbcd-134">Реализация <xref:System.Windows.Controls.UserControl> ,`AddInUI`, показана в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="0cbcd-135">Реализация `IWPFAddInView.GetAddInUI` надстройки просто должна возвращать новый `AddInUI`экземпляр, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="0cbcd-136">Реализация ведущего приложения</span><span class="sxs-lookup"><span data-stu-id="0cbcd-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="0cbcd-137">При создании адаптера на стороне узла и представления узла ведущее приложение может использовать модель надстройки .NET Framework, чтобы открыть конвейер, получить представление надстройки и вызвать `IWPFAddInHostView.GetAddInUI` метод.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="0cbcd-138">Эти действия показаны в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cbcd-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="0cbcd-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0cbcd-139">See also</span></span>

- <span data-ttu-id="0cbcd-140">[Надстройки и расширения среды](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="0cbcd-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="0cbcd-141">Общие сведения о надстройках WPF</span><span class="sxs-lookup"><span data-stu-id="0cbcd-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
