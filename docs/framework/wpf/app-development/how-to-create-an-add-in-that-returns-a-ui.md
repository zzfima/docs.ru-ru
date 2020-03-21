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
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174593"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a>Практическое руководство. Создание надстройки, возвращающей пользовательский интерфейс
В этом примере показано, как создать надстройку, которая возвращает Фонд презентации Windows (WPF) в отдельное приложение WPF.  
  
 Надстройка возвращает пользовательский интерфейс, который является пользовательским элементом WPF. Содержимое пользовательского элемента управления составляет одна кнопка, при нажатии которой отображается окно сообщения. Автономное приложение WPF размещает надстройку и отображает пользовательский элемент управления (возвращенный надстройкой) в качестве содержимого основного окна приложения.  
  
 **Предварительные требования**  
  
 В этом примере выделены расширения WPF к модели надстройки .NET, которая позволяет этот сценарий, и предполагается следующее:  
  
- Знание модели надстройки .NET Framework, включая конвейер, надстройку и разработку хоста. Если вы не знакомы с этими понятиями, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) Для руководства, демонстрирующего реализацию конвейера, надстройки и приложения-хоста, [см.](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))  
  
- Знание расширений WPF к модели надстройки .NET Framework, которое можно найти здесь: [Обзор надсмов WPF Add-Ins.](wpf-add-ins-overview.md)  
  
## <a name="example"></a>Пример  
 Для создания надстройки, возвращающему UPF UI, необходим определенный код для каждого сегмента конвейера, надстройки и приложения для узла.  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a>Реализация сегмента конвейера контракта  
 Метод должен быть определен договором о возврате uI, а <xref:System.AddIn.Contract.INativeHandleContract>его стоимость возврата должна быть типа. Об этом свидетельствует `GetAddInUI` метод `IWPFAddInContract` договора в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a>Реализация сегмента конвейера представления надстройки  
 Поскольку надстройка реализует UI, которые он <xref:System.Windows.FrameworkElement>предоставляет в качестве подклассов, метод на `IWPFAddInView.GetAddInUI` представлении надстройки, который соотносится с должны вернуть значение типа. <xref:System.Windows.FrameworkElement> В следующем коде показано представление надстройки контракта, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера надстройки  
 Метод контракта возвращает <xref:System.AddIn.Contract.INativeHandleContract>, но надстройка <xref:System.Windows.FrameworkElement> возвращает a (как указано в представлении надстройки). Следовательно, <xref:System.Windows.FrameworkElement> необходимо быть преобразованы в <xref:System.AddIn.Contract.INativeHandleContract> перед пересечением границы изоляции. Эта работа выполняется адаптером-подрабатывал по вызову, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a>Реализация сегмента конвейера представления в ведущем приложении  
 Поскольку в приложении-хостах будет отображаться метод на представлении <xref:System.Windows.FrameworkElement>узла, который соотносится `IWPFAddInHostView.GetAddInUI` с должен вернуть значение типа. <xref:System.Windows.FrameworkElement> В следующем коде показано представление контракта в основном приложении, реализованное как интерфейс.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a>Реализация сегмента конвейера адаптера приложения  
 Метод контракта <xref:System.AddIn.Contract.INativeHandleContract>возвращает, но приложение хоста ожидает <xref:System.Windows.FrameworkElement> (как указано в представлении хоста). Следовательно, <xref:System.AddIn.Contract.INativeHandleContract> необходимо быть преобразованы в <xref:System.Windows.FrameworkElement> после пересечения границы изоляции. Эта работа выполняется адаптером на <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>стороне хоста путем вызова, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a>Реализация надстройки  
 При создании адаптера и представления надстройки надстройки`WPFAddIn1.AddIn`() `IWPFAddInView.GetAddInUI` должен быть <xref:System.Windows.FrameworkElement> реализован <xref:System.Windows.Controls.UserControl> метод возврата объекта (в этом примере). Реализация <xref:System.Windows.Controls.UserControl>, `AddInUI`показано на следующем коде.  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 Реализация `IWPFAddInView.GetAddInUI` надстройки просто должна вернуть новый `AddInUI`экземпляр, как показано в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a>Реализация ведущего приложения  
 При создании адаптера-хоста и представления хоста приложение может использовать модель надстройки .NET Framework для открытия конвейера, приобретения представления о надстройке и вызова метода. `IWPFAddInHostView.GetAddInUI` Эти действия показаны в следующем коде.  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a>См. также раздел

- [Надстройки и расширения среды](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Общие сведения о надстройках WPF](wpf-add-ins-overview.md)
