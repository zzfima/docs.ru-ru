---
title: Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: b0e847061a30e93d36997ab603c52715e2730765
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182639"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
В этом примере показано, как создать надстройку, которая является Windows Presentation Foundation (WPF), размещенной в автономном приложении WPF.  
  
 Надстройка — это пользовательский интерфейс, который является пользовательским элементом управления WPF. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. Автономное приложение WPF размещает Пользовательский интерфейс надстройки как содержимое главного окна приложения.  
  
 **Необходимые компоненты**  
  
 В этом примере расширения WPF выделены для модели надстройки .NET Framework, которая включает этот сценарий и предполагает следующее:  
  
- Знание модели надстроек .NET Framework, включая конвейер, надстройку и разработку на узле. Если вы не знакомы с этими понятиями, см. раздел [надстройки и расширяемость](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Руководство, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, см. в разделе [пошаговое руководство. Создание расширяемого приложения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Знание расширений WPF для модели надстройки .NET Framework. См. раздел [Общие сведения о надстройках WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Пример  
 Чтобы создать надстройку, которая является пользовательским интерфейсом WPF, требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта

Когда надстройка является пользовательским интерфейсом, контракт для надстройки должен реализовать <xref:System.AddIn.Contract.INativeHandleContract>. В примере `IWPFAddInContract` реализует <xref:System.AddIn.Contract.INativeHandleContract>, как показано в следующем коде.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки

Поскольку надстройка реализуется как подкласс <xref:System.Windows.FrameworkElement> типа, представление надстройки также должно быть подклассом. <xref:System.Windows.FrameworkElement> В следующем коде показано представление надстройки контракта, реализованное как `WPFAddInView` класс.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
Здесь представление надстройки является производным от <xref:System.Windows.Controls.UserControl>. Следовательно, Пользовательский интерфейс надстройки также должен быть производным от <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки

Хотя контракт является <xref:System.AddIn.Contract.INativeHandleContract>, надстройка представляет собой <xref:System.Windows.FrameworkElement> (как указано в сегменте конвейера представления надстройки). Поэтому перед<xref:System.AddIn.Contract.INativeHandleContract> пересечением границы изоляции <xref:System.Windows.FrameworkElement> необходимо преобразовать в. Эта работа выполняется с помощью адаптера надстройки путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, как показано в следующем коде.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

В модели надстройки, где надстройка возвращает пользовательский интерфейс (см. раздел [Создание надстройки, возвращающей пользовательский интерфейс](how-to-create-an-add-in-that-returns-a-ui.md)), адаптер надстройки преобразует <xref:System.Windows.FrameworkElement> в <xref:System.AddIn.Contract.INativeHandleContract> в с помощью вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>также должен вызываться в этой модели, хотя необходимо реализовать метод для написания кода для его вызова. <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> Это делается путем переопределения и реализации кода, который вызывает <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> , если вызывающий <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> код ожидает <xref:System.AddIn.Contract.INativeHandleContract>. В этом случае вызывающий объект будет адаптером приложения, который рассматривается в следующем подразделе.  
  
> [!NOTE]
> Также необходимо переопределить <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> в этой модели, чтобы обеспечить переход между интерфейсом пользователя ведущего приложения и надстройкой пользовательского интерфейса. Дополнительные сведения см. в разделе "ограничения надстроек WPF" раздела [Общие сведения о](wpf-add-ins-overview.md)надстройках WPF.  
  
Так как адаптер надстройки реализует интерфейс, производный от <xref:System.AddIn.Contract.INativeHandleContract>, также необходимо реализовать <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, хотя он игнорируется при <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> переопределении.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в основном приложении

В этой модели ведущее приложение обычно принимает представление главного приложения в <xref:System.Windows.FrameworkElement> подкласс. Адаптер на стороне главного приложения должен преобразовать <xref:System.AddIn.Contract.INativeHandleContract> в объект <xref:System.Windows.FrameworkElement> после <xref:System.AddIn.Contract.INativeHandleContract> пересечения границы изоляции. Так как метод не вызывается ведущим приложением для получения <xref:System.Windows.FrameworkElement>, представление главного приложения должно "возвращать" объект <xref:System.Windows.FrameworkElement> , содержащий его. Следовательно, представление главного приложения должно быть производным от подкласса <xref:System.Windows.FrameworkElement> , который может содержать другие пользовательские интерфейсы, <xref:System.Windows.Controls.UserControl>такие как. В следующем коде показано ведущее представление контракта, реализованное как `WPFAddInHostView` класс.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения

Хотя контракт является <xref:System.AddIn.Contract.INativeHandleContract>, ведущее приложение ждет <xref:System.Windows.Controls.UserControl> (как указано представлением главного приложения). Следовательно, <xref:System.Windows.FrameworkElement>необходимопреобразовать в после пересечения границы изоляции до того, как будет задано содержимое представления узла (которое является производным от <xref:System.Windows.Controls.UserControl>). <xref:System.AddIn.Contract.INativeHandleContract>  
  
Эту работу выполняет адаптер приложения, как показано в следующем коде.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Как видите, адаптер на стороне главного приложения получает объект <xref:System.AddIn.Contract.INativeHandleContract> , вызывая <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> метод адаптера надстройки (это точка <xref:System.AddIn.Contract.INativeHandleContract> пересечения границы изоляции).  
  
Затем адаптер на стороне узла преобразует <xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> в в, вызвав <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Наконец, <xref:System.Windows.FrameworkElement> задается как содержимое представления главного приложения.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Реализация надстройки

При наличии адаптера надстройки и представления надстройки можно реализовать надстройку, производя ее от представления надстройки, как показано в следующем коде.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

В этом примере можно увидеть одно интересное преимущество этой модели: разработчикам надстроек требуется только реализовать надстройку (поскольку это также пользовательский интерфейс), а не как класс надстройки, так и пользовательский интерфейс надстройки.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения

При создании адаптера на стороне узла и представления главного приложения ведущее приложение может использовать модель надстройки .NET Framework, чтобы открыть конвейер и получить представление надстройки в основном приложении. Эти действия показаны в следующем коде.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

Ведущее приложение использует стандартный код модели надстройки .NET Framework для активации надстройки, которая неявно возвращает ведущее представление ведущему приложению. Ведущее приложение впоследствии отображает представление узла (то есть <xref:System.Windows.Controls.UserControl>) <xref:System.Windows.Controls.Grid>из.  
  
 Код для обработки взаимодействия с пользовательским интерфейсом надстройки выполняется в домене приложения надстройки. Эти взаимодействия включают следующее.  
  
- <xref:System.Windows.Controls.Button> Обработка<xref:System.Windows.Controls.Primitives.ButtonBase.Click> события.  
  
- <xref:System.Windows.MessageBox>Отображение.  
  
 Это действие полностью изолировано от ведущего приложения.  
  
## <a name="see-also"></a>См. также

- [Надстройки и расширения среды](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Общие сведения о надстройках WPF](wpf-add-ins-overview.md)
