---
title: Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
ms.date: 03/30/2017
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: 4bd03c2f879ecab83306bb68552c044a33f2e6e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a>Практическое руководство. Создание надстройки, являющейся пользовательским интерфейсом
В этом примере показано, как создать надстройку, Windows Presentation Foundation (WPF), размещаемый в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автономное приложение.  
  
 Надстройка — это [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] пользовательский элемент управления. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Автономное приложение размещает надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] как содержимое главного окна приложения.  
  
 **Необходимые компоненты**  
  
 В этом примере выделяет [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширения для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, поддерживающей этот сценарий и предполагается следующее:  
  
-   Знание [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, включая конвейера, надстройки и разработку ведущего приложения. Если вы не знакомы с этими понятиями, см. раздел [надстройки и расширения](../../../../docs/framework/add-ins/index.md). Учебник, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, в разделе [Пошаговое руководство: Создание расширяемого приложения](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Знание [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, которые можно найти здесь: [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Пример  
 Чтобы создать надстройку, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта  
 Если надстройка имеет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], должны реализовывать контракт надстройки <xref:System.AddIn.Contract.INativeHandleContract>. В примере `IWPFAddInContract` реализует <xref:System.AddIn.Contract.INativeHandleContract>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInIsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]  
  
<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки  
 Надстройка реализована как подкласс <xref:System.Windows.FrameworkElement> тип, представление надстройки также должно быть подклассом <xref:System.Windows.FrameworkElement>. В следующем коде показано представление надстройки контракта, реализованное как `WPFAddInView` класса.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
  
 Здесь представление надстройки является производным от <xref:System.Windows.Controls.UserControl>. Следовательно, надстройка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] также должен быть производным от <xref:System.Windows.Controls.UserControl>.  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки  
 Контракт представляет <xref:System.AddIn.Contract.INativeHandleContract>, надстройка — это <xref:System.Windows.FrameworkElement> (как указано в сегмент представления надстройки конвейера). Таким образом <xref:System.Windows.FrameworkElement> должны быть преобразованы в <xref:System.AddIn.Contract.INativeHandleContract> до пересечения границы изоляции. Эта работа выполняется адаптером стороне надстройки путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
  
 В модели надстройки, где надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] (см. [Создайте надстройку, возвращает пользовательский Интерфейс](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md)), адаптер надстройки преобразовать <xref:System.Windows.FrameworkElement> для <xref:System.AddIn.Contract.INativeHandleContract> путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> необходимо также вызвать в этой модели, несмотря на то, что необходимо реализовать метод, с которых можно написать код, который будет вызывать его. Это делается путем переопределения <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> и реализация кода, который вызывает <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> Если код, вызывающий <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> ожидает <xref:System.AddIn.Contract.INativeHandleContract>. В этом случае вызывающий объект будет адаптером приложения, который рассматривается в следующем подразделе.  
  
> [!NOTE]
>  Необходимо также переопределить <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> в этой модели, чтобы разрешить переходы между ведущим приложением [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и надстройка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Дополнительные сведения см. в разделе «WPF надстройки ограничения» в [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Так как адаптер со стороны надстройки реализует интерфейс, который является производным от <xref:System.AddIn.Contract.INativeHandleContract>, необходимо также реализовать <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, несмотря на то, что этот параметр учитывается при <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> переопределяется.  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в основном приложении  
 В этой модели ведущее приложение обычно ожидает, что представление узла к <xref:System.Windows.FrameworkElement> подкласс. Адаптер хоста необходимо преобразовать <xref:System.AddIn.Contract.INativeHandleContract> для <xref:System.Windows.FrameworkElement> после <xref:System.AddIn.Contract.INativeHandleContract> пересекает границу изоляции. Поскольку метод не вызывается ведущим приложением для получения <xref:System.Windows.FrameworkElement>, хост-представление должно «return» <xref:System.Windows.FrameworkElement> , включая его. Следовательно, представление узла должен быть производным от подкласс <xref:System.Windows.FrameworkElement> , могут содержать другие [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], такие как <xref:System.Windows.Controls.UserControl>. В следующем коде показано представление узла контракта, реализованный как `WPFAddInHostView` класса.  
  
  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения  
 Контракт представляет <xref:System.AddIn.Contract.INativeHandleContract>, а ведущее приложение ожидает <xref:System.Windows.Controls.UserControl> (как указано в представлении узлов). Следовательно <xref:System.AddIn.Contract.INativeHandleContract> должны быть преобразованы в <xref:System.Windows.FrameworkElement> после пересечения границы изоляции перед заданием в качестве содержимого хост-представления (который является производным от <xref:System.Windows.Controls.UserControl>).  
  
 Эту работу выполняет адаптер приложения, как показано в следующем коде.  
  
  
  
 Как видите, адаптер получает <xref:System.AddIn.Contract.INativeHandleContract> путем вызова адаптер на стороне надстройки <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> метод (это точка где <xref:System.AddIn.Contract.INativeHandleContract> пересекает границу изоляции).  
  
 Адаптер хоста затем преобразует <xref:System.AddIn.Contract.INativeHandleContract> для <xref:System.Windows.FrameworkElement> путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Наконец <xref:System.Windows.FrameworkElement> задается как содержимое хост-представления.  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Реализация надстройки  
 При наличии адаптера надстройки и представления надстройки можно реализовать надстройку, производя ее от представления надстройки, как показано в следующем коде.  
  
  
  
  
  
 Из этого примера, вы увидите интересные преимуществом этой модели: разработчикам необходимо только реализовать надстройку (так как это [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] также), а не класс надстройки и add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="HostApp"></a>   
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения  
 С помощью адаптера и созданного представления узла, ведущее приложение может использовать [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстройки для открытия канала и получения представления узла надстройки. Эти действия показаны в следующем коде.  
  
  
  
 Ведущее приложение использует обычный [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] код модели надстройки, чтобы активировать надстройку, которая неявным образом возвращает хост-представление ведущего приложения. Ведущее приложение затем отображает хост-представление (который является <xref:System.Windows.Controls.UserControl>) из <xref:System.Windows.Controls.Grid>.  
  
 Код для обработки взаимодействия с надстройкой [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] выполняется в домене приложения надстройки. Эти взаимодействия включают следующее.  
  
-   Обработка <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий.  
  
-   Отображение <xref:System.Windows.MessageBox>.  
  
 Это действие полностью изолировано от ведущего приложения.  
  
## <a name="see-also"></a>См. также  
 [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md)  
 [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
