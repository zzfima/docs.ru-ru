---
title: "Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "надстройка [WPF], возвращает пользовательский интерфейс"
  - "создание надстройки, возвращающей пользовательский интерфейс [WPF]"
  - "реализация сегментов конвейера надстройки [WPF]"
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс
В этом примере показано, как создать надстройку, возвращающую [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] в узел автономного приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], представляющий собой пользовательский элемент управления [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения.  The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] standalone application hosts the add\-in and displays the user control \(returned by the add\-in\) as the content of the main application window.  
  
 **Предварительные требования**  
  
 В этом примере акцентируются расширения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], поддерживающей этот скрипт, и предполагается соблюдение следующих условий:  
  
-   Знание модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], включая конвейер, надстройку и разработку ведущего приложения.  Для ознакомления с этими понятиями см. раздел [Надстройки и расширения среды](../../../../ml/index.xml).  Руководство, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, см. в разделе [Пошаговое руководство. Создание расширяемого приложения](../Topic/Walkthrough:%20Creating%20an%20Extensible%20Application.md).  
  
-   Знание расширений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], которые можно найти в разделе [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
## Пример  
 Чтобы создать надстройку, возвращающую[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Contract"></a>   
## Реализация сегмента конвейера «контракт»  
 Метод должен быть определен контрактом для возвращения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], и возвращаемое значение должно иметь тип <xref:System.AddIn.Contract.INativeHandleContract>.  Это демонстрируется методом `GetAddInUI` для `IWPFAddInContract` контракта в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## Реализация сегмента конвейера «представление надстройки»  
 Поскольку надстройка реализует [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], она предоставляет в качестве подклассов <xref:System.Windows.FrameworkElement>, метод представления надстройки, соответствующий `IWPFAddInView.GetAddInUI`, должен возвращать значение типа <xref:System.Windows.FrameworkElement>.  В следующем коде показано представление надстройки контракта, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## Реализация сегмента конвейера «адаптер на стороне надстройки»  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но надстройка возвращает <xref:System.Windows.FrameworkElement> \(как указано представлением надстройки\).  Следовательно, <xref:System.Windows.FrameworkElement> должен быть преобразован в <xref:System.AddIn.Contract.INativeHandleContract> прежде чем будет пересечена граница изоляции.  Эту работу выполняет адаптер на стороне надстройки, вызывая <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> \(как показано в следующем коде\).  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## Реализация сегмента конвейера «хост\-представление»  
 Так как в главное приложение будет отображать <xref:System.Windows.FrameworkElement>, метод представления узла соответствующего `IWPFAddInHostView.GetAddInUI` должен возвращать значение типа <xref:System.Windows.FrameworkElement>.  В следующем коде показано представление узла контракта, реализованный как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## Реализация сегмента конвейера «адаптер на стороне сайта»  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но главное приложение ожидает <xref:System.Windows.FrameworkElement> \(как указано представлением узла\).  Следовательно, <xref:System.AddIn.Contract.INativeHandleContract> должен быть преобразован в <xref:System.Windows.FrameworkElement> после пересечения границы изоляции.  Эта работа выполняется с помощью адаптера узла путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## Реализация надстройки  
 С помощью адаптера надстройки и созданного представления надстройки, надстройка \(`WPFAddIn1.AddIn`\) должна реализовать `IWPFAddInView.GetAddInUI` метод для возврата <xref:System.Windows.FrameworkElement> объекта \( <xref:System.Windows.Controls.UserControl> в этом примере\).  Реализация интерфейса `AddInUI` <xref:System.Windows.Controls.UserControl> показывается с помощью следующего кода.  
  
 [!code-xml[SimpleAddInReturnsAUISample#AddInUIMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Реализации `IWPFAddInView.GetAddInUI` посредством надстройки требуется новый экземпляр `AddInUI`, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## Реализация ведущего приложения  
 С помощью адаптера и созданного представления узла, ведущее приложение может использовать [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] модель надстройки для открытия канала, получения представления узла надстройки и вызова `IWPFAddInHostView.GetAddInUI` метода.  Эти действия показаны в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## См. также  
 [Надстройки и расширения среды](../../../../ml/index.xml)   
 [Общие сведения о надстройках WPF](../../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md)