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
ms.openlocfilehash: d799c91b9abdf7882a0fcd3f0b656eac553b188c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460146"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс
В этом примере показано, как создать надстройку, которая возвращает Windows Presentation Foundation (WPF) в изолированное приложение WPF узла.  
  
 Надстройка возвращает пользовательский интерфейс, который является пользовательским элементом управления WPF. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. Автономное приложение WPF размещает надстройку и отображает пользовательский элемент управления (возвращаемый надстройкой) в качестве содержимого главного окна приложения.  
  
 **Необходимые компоненты**  
  
 В этом примере расширения WPF выделены для модели надстройки .NET Framework, которая включает этот сценарий и предполагает следующее:  
  
- Знание модели надстроек .NET Framework, включая конвейер, надстройку и разработку на узле. Если вы не знакомы с этими понятиями, см. раздел [надстройки и расширяемость](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)). Руководство, в котором демонстрируется реализация конвейера, надстройки и ведущего приложения, см. в разделе [Пошаговое руководство. Создание расширяемого приложения](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).  
  
- Сведения о расширениях WPF для модели надстройки .NET Framework, которую можно найти здесь: [Обзор надстроек WPF](wpf-add-ins-overview.md).  
  
## <a name="example"></a>Пример  
 Чтобы создать надстройку, которая возвращает пользовательский интерфейс WPF, требуется специальный код для каждого сегмента конвейера, надстройки и ведущего приложения.  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта  
 Метод должен быть определен контрактом для возврата пользовательского интерфейса, и его возвращаемое значение должно иметь тип <xref:System.AddIn.Contract.INativeHandleContract>. Это продемонстрировано в методе `GetAddInUI` контракта `IWPFAddInContract` в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки  
 Поскольку надстройка реализует пользовательские интерфейсы, предоставляемые в качестве подклассов <xref:System.Windows.FrameworkElement>, метод в представлении надстройки, соответствующий `IWPFAddInView.GetAddInUI`, должен возвращать значение типа <xref:System.Windows.FrameworkElement>. В следующем коде показано представление надстройки контракта, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но надстройка возвращает <xref:System.Windows.FrameworkElement> (как указано в представлении надстройки). Следовательно, перед пересечением границы изоляции <xref:System.Windows.FrameworkElement> необходимо преобразовать в <xref:System.AddIn.Contract.INativeHandleContract>. Эта работа выполняется адаптером надстройки путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в основном приложении  
 Поскольку ведущее приложение будет отображать <xref:System.Windows.FrameworkElement>, метод в представлении узла, соответствующий `IWPFAddInHostView.GetAddInUI`, должен возвращать значение типа <xref:System.Windows.FrameworkElement>. В следующем коде показано представление контракта в основном приложении, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но ведущее приложение ждет <xref:System.Windows.FrameworkElement> (как указано представлением главного приложения). Следовательно, <xref:System.AddIn.Contract.INativeHandleContract> необходимо преобразовать в <xref:System.Windows.FrameworkElement> после пересечения границы изоляции. Эта работа выполняется адаптером на стороне главного приложения путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a>Реализация надстройки  
 После создания адаптера надстройки и представления надстроек надстройка (`WPFAddIn1.AddIn`) должна реализовать метод `IWPFAddInView.GetAddInUI` для возврата <xref:System.Windows.FrameworkElement> объекта (<xref:System.Windows.Controls.UserControl> в этом примере). Реализация <xref:System.Windows.Controls.UserControl>, `AddInUI`, показана в следующем коде.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Реализация `IWPFAddInView.GetAddInUI` надстройкой просто должна возвращать новый экземпляр `AddInUI`, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения  
 При создании адаптера на стороне узла и представления узла ведущее приложение может использовать модель надстройки .NET Framework, чтобы открыть конвейер, получить представление надстройки и вызвать метод `IWPFAddInHostView.GetAddInUI`. Эти действия показаны в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>См. также

- [Надстройки и расширения среды](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Общие сведения о надстройках WPF](wpf-add-ins-overview.md)
