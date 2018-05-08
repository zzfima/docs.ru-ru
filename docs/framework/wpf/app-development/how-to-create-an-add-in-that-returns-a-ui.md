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
ms.openlocfilehash: 24b30d61553796840a44a869eacb33232a0b78d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс
В этом примере показано, как создать надстройку, возвращающий Windows Presentation Foundation (WPF) на узле [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автономное приложение.  
  
 Надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] пользовательский элемент управления. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Автономное приложение размещает надстройки и отображает пользовательский элемент управления (возвращается методом надстройки) как содержимое главного окна приложения.  
  
 **Необходимые компоненты**  
  
 В этом примере выделяет [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширения для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, поддерживающей этот сценарий и предполагается следующее:  
  
-   Знание [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, включая конвейера, надстройки и разработку ведущего приложения. Если вы не знакомы с этими понятиями, см. раздел [надстройки и расширения](../../../../docs/framework/add-ins/index.md). Учебник, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, в разделе [Пошаговое руководство: Создание расширяемого приложения](../../../../docs/framework/add-ins/walkthrough-create-extensible-app.md).  
  
-   Знание [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстроек, которые можно найти здесь: [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## <a name="example"></a>Пример  
 Чтобы создать надстройку, которая возвращает [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.  
    
  
<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта  
 Метод должен быть определен в контракте для возвращения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], и должен иметь тип возвращаемого значения <xref:System.AddIn.Contract.INativeHandleContract>. Это продемонстрировано на `GetAddInUI` метод `IWPFAddInContract` контракта в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки  
 Поскольку надстройка реализует [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] предоставляет в качестве подклассов <xref:System.Windows.FrameworkElement>, метод представления надстройки, соответствующее `IWPFAddInView.GetAddInUI` должен возвращать значение типа <xref:System.Windows.FrameworkElement>. В следующем коде показано представление надстройки контракта, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но Надстройка возвращает <xref:System.Windows.FrameworkElement> (как указано представлением надстройки). Следовательно <xref:System.Windows.FrameworkElement> должны быть преобразованы в <xref:System.AddIn.Contract.INativeHandleContract> до пересечения границы изоляции. Эта работа выполняется адаптером стороне надстройки путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в основном приложении  
 Поскольку ведущее приложение будет отображаться <xref:System.Windows.FrameworkElement>, метод представления узла, которое связано с `IWPFAddInHostView.GetAddInUI` должен возвращать значение типа <xref:System.Windows.FrameworkElement>. В следующем коде показано представление контракта в основном приложении, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, а ведущее приложение ожидает <xref:System.Windows.FrameworkElement> (как указано в представлении узлов). Следовательно <xref:System.AddIn.Contract.INativeHandleContract> должны быть преобразованы в <xref:System.Windows.FrameworkElement> после пересечения границы изоляции. Эта работа осуществляется адаптера узла путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Реализация надстройки  
 С помощью адаптера на стороне надстройки и надстройка представления создания надстройки (`WPFAddIn1.AddIn`) должен реализовывать `IWPFAddInView.GetAddInUI` метод для возврата <xref:System.Windows.FrameworkElement> объекта ( <xref:System.Windows.Controls.UserControl> в этом примере). Реализация <xref:System.Windows.Controls.UserControl>, `AddInUI`, показано в следующем примере кода.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Реализация `IWPFAddInView.GetAddInUI` надстройкой просто должно возвращать новый экземпляр `AddInUI`, как показано в следующем примере кода.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения  
 С помощью адаптера и созданного представления узла, ведущее приложение может использовать [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстройки для открытия канала, получения представления узла надстройки, и вызовите `IWPFAddInHostView.GetAddInUI` метод. Эти действия показаны в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>См. также  
 [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md)  
 [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)
