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
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141033"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
В этом примере показано, как создать надстройку, которая является Фондом презентаций Windows (WPF), который размещается автономным приложением WPF.  
  
 Надстройка — это пользовательский интерфейс, который является пользовательским контролем WPF. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. Автономное приложение WPF размещает uI надстройки в качестве содержимого основного окна приложения.  
  
 **Предварительные требования**  
  
 В этом примере выделены расширения WPF к модели надстройки .NET, которая позволяет этот сценарий, и предполагается следующее:  
  
- Знание модели надстройки .NET Framework, включая конвейер, надстройку и разработку хоста. Если вы не знакомы с этими понятиями, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) Для руководства, демонстрирующего реализацию конвейера, надстройки и приложения-хоста, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))  
  
- Знание расширений WPF в модели надстройки .NET. Смотрите [обзор WPF Add-Ins.](wpf-add-ins-overview.md)  
  
## <a name="example"></a>Пример  
 Для создания надстройки, которая является UI WPF, требуется определенный код для каждого сегмента конвейера, надстройки и приложения для узла.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта

Когда надстройка — это ui, контракт на надстройку должен быть реализован. <xref:System.AddIn.Contract.INativeHandleContract> В примере `IWPFAddInContract` <xref:System.AddIn.Contract.INativeHandleContract>реализуется, как показано в следующем коде.  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки

Поскольку надстройка реализована как подкласс <xref:System.Windows.FrameworkElement> типа, представление надстройки <xref:System.Windows.FrameworkElement>также должно подклассифицироваться. Следующий код показывает надстройку контракта, реализованную `WPFAddInView` как класс.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
Здесь приведен вид надстройки, <xref:System.Windows.Controls.UserControl>полученный из . Следовательно, надстройка uI должна <xref:System.Windows.Controls.UserControl>также вытекать из .  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки

В то время <xref:System.AddIn.Contract.INativeHandleContract>как контракт является <xref:System.Windows.FrameworkElement> дополнением (как указано в сегменте простройки представления конвейера). Таким образом, <xref:System.Windows.FrameworkElement> должны быть <xref:System.AddIn.Contract.INativeHandleContract> преобразованы в перед пересечением границы изоляции. Эта работа выполняется адаптером-подрабатывал по вызову, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>как показано в следующем коде.  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

В модели надстройки, где надстройка возвращает uI (см. [Создать надстройку,](how-to-create-an-add-in-that-returns-a-ui.md)которая <xref:System.Windows.FrameworkElement> возвращает <xref:System.AddIn.Contract.INativeHandleContract> uI), адаптер надстройки преобразовал сяочку, позвонив. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>также должны быть вызваны в этой модели, хотя вам нужно реализовать метод, из которого написать код, чтобы вызвать его. Вы делаете это, <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> переопределяя <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и реализуя <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> код, <xref:System.AddIn.Contract.INativeHandleContract>который вызывает, если код, который вызывает ожидает . В этом случае вызывающий объект будет адаптером приложения, который рассматривается в следующем подразделе.  
  
> [!NOTE]
> Кроме того, необходимо <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> переопределить в этой модели, чтобы включить табуирование между uI-разновидномых приложений-хоста и uI надстройки. Для получения дополнительной информации см. [WPF Add-Ins Overview](wpf-add-ins-overview.md)  
  
Поскольку надстройка адаптера реализует интерфейс, <xref:System.AddIn.Contract.INativeHandleContract>который вытекает из, вы также должны реализовать, <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>хотя это игнорируется, когда <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> переопределяется.  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в ведущем приложении

В этой модели приложение хоста обычно ожидает, <xref:System.Windows.FrameworkElement> что представление узла будет подклассом. Адаптер стороны хоста <xref:System.AddIn.Contract.INativeHandleContract> должен <xref:System.Windows.FrameworkElement> преобразовать его в после пересечения <xref:System.AddIn.Contract.INativeHandleContract> границы изоляции. Поскольку метод не вызывается хост-приложением для <xref:System.Windows.FrameworkElement>получения, представление <xref:System.Windows.FrameworkElement> узла должно "вернуть" его, содержа его. Следовательно, представление узла должно вытекать <xref:System.Windows.FrameworkElement> из подкласса, который <xref:System.Windows.Controls.UserControl>может содержать другие uIs, такие как . Следующий код показывает представление узла контракта, `WPFAddInHostView` реализованного как класс.  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения

В то время <xref:System.AddIn.Contract.INativeHandleContract>как контракт является, хост приложение ожидает <xref:System.Windows.Controls.UserControl> (как указано в представлении хоста). Следовательно, <xref:System.AddIn.Contract.INativeHandleContract> необходимо преобразовать <xref:System.Windows.FrameworkElement> в после пересечения границы изоляции, прежде чем установить <xref:System.Windows.Controls.UserControl>в качестве содержания вида хоста (который вытекает из).  
  
Эту работу выполняет адаптер приложения, как показано в следующем коде.  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

Как вы можете видеть, адаптер на <xref:System.AddIn.Contract.INativeHandleContract> стороне хоста приобретает, вызывая <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> метод адаптера надстройки (это точка, где <xref:System.AddIn.Contract.INativeHandleContract> пересекает границу изоляции).  
  
Адаптер на стороне хоста <xref:System.AddIn.Contract.INativeHandleContract> преобразует <xref:System.Windows.FrameworkElement> сярприз в вызов. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> Наконец, <xref:System.Windows.FrameworkElement> настроен как содержимое представления узла.  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Реализация надстройки

При наличии адаптера надстройки и представления надстройки можно реализовать надстройку, производя ее от представления надстройки, как показано в следующем коде.  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

В этом примере можно увидеть одно интересное преимущество этой модели: разработчикам надстройки нужно реализовать только надстройку (поскольку это также используется пользовательский доступ), а не как класс надстройки, так и надстройку.  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения

При создании адаптера-хоста и представления хоста приложение может использовать модель надстройки .NET Framework для открытия конвейера и получения представления о надстройке. Эти действия показаны в следующем коде.  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

Для активации надстройки, которая неявно возвращает представление хоста в приложение хоста, используется типовой код модели надстройки .NET Framework. Впоследствии хост-приложение отображает представление <xref:System.Windows.Controls.UserControl>хоста <xref:System.Windows.Controls.Grid>(который является) от .  
  
 Код для обработки взаимодействий с uI надстройки работает в домене приложения надстройки. Эти взаимодействия включают следующее.  
  
- Обработка <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события.  
  
- Отображение <xref:System.Windows.MessageBox>.  
  
 Это действие полностью изолировано от ведущего приложения.  
  
## <a name="see-also"></a>См. также раздел

- [Надстройки и расширения среды](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Общие сведения о надстройках WPF](wpf-add-ins-overview.md)
