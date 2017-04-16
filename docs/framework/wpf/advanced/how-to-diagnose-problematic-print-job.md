---
title: "Практическое руководство. Диагностика проблем при выполнении заданий печати | Microsoft Docs"
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
  - "задания печати, диагностика проблем"
  - "задания печати, устранение неполадок"
  - "устранение неполадок заданий печати"
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Диагностика проблем при выполнении заданий печати
Часто администраторы сети получают жалобы от пользователей по поводу заданий печати, которые не выполняются или выполняются медленно.  В интерфейсе [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] представлен широкий набор свойств заданий печати, обеспечивающих быструю удаленную диагностику заданий печати.  
  
## Пример  
 Ниже приведены основные этапы по созданию служебной программы такого рода.  
  
1.  Идентификация задания печати, на которое жалуется пользователь.  Часто пользователи не могут сделать это точно.  Они могут не знать имена серверов печати или принтеров.  Пользователи могут описывать расположение принтера в терминологии отличной от той, которая была использована при установке свойства <xref:System.Printing.PrintQueue.Location%2A>.  В связи с этим рекомендуется создавать список текущих заданий, принятых от пользователей.  При наличии нескольких заданий выявление проблемного задания может осуществляться во взаимодействии пользователя и администратора системы печати.  Ниже приведены соответствующие промежуточные этапы.  
  
    1.  Получите список всех серверов печати.  
  
    2.  Выполните цикл опроса серверов об их очередях печати.  
  
    3.  На каждом шаге цикла выполните цикл опроса заданий во всех очередях сервера.  
  
    4.  На каждом шаге цикла опроса очередей выполните цикл опроса всех заданий и соберите идентифицирующие сведения о заданиях, отправленных жалующимся пользователем.  
  
2.  При выявлении проблемного задания печати просмотрите соответствующие свойства для определения источника проблемы.  Например, задание может находиться в состоянии ошибки, или перед печатью задания выключен принтер, обслуживающий очередь.  
  
 В приведенном ниже коде представлен ряд примеров.  В первом примере кода представлен цикл опроса очередей печати.  \(Шаг «1в» выше.\) Переменная `myPrintQueues` представляет собой объект класса <xref:System.Printing.PrintQueueCollection> для текущего сервера печати.  
  
 Пример кода начинается с обновления текущего объекта очереди печати с помощью метода <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=fullName>.  Это гарантирует точное представление состояния соответствующего физического принтера с помощью свойств объекта.  Затем в приложении извлекается текущая коллекцию заданий печати в очереди с помощью метода <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>.  
  
 После этого в приложении просматривается коллекция <xref:System.Printing.PrintSystemJobInfo>, каждое свойство <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> в которой сравнивается с псевдонимом жалующегося пользователя.  Если они совпадают, идентифицирующие сведения о задании добавляются к соответствующей строке.  \(Переменные `userName` и `jobList` инициализируются в приложении ранее.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 В следующем примере выбирается приложение на шаге 2.  \(См. выше.\) После определения проблемного задания в приложении запрашиваются сведения, которые будут идентифицировать это задание.  На основании этих сведений создаются объекты <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue> и <xref:System.Printing.PrintSystemJobInfo>.  
  
 На этом этапе в приложении содержится структура ветвления, соответствующая двум способам проверки состояния задачи печати:  
  
-   чтение флагов свойства <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>, имеющего тип <xref:System.Printing.PrintJobStatus>;  
  
-   чтение каждого соответствующего свойства, например <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> и <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>.  
  
 В этом примере демонстрируются оба метода. Пользователь имеет возможность заранее выбрать используемый метод \(чтобы использовать флаги свойства <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>, следует выбрать ответ «Y»\).  Ниже приведены сведения об этих двух методах.  В завершение, в приложении используется метод **ReportQueueAndJobAvailability** для определения возможности печати задания в это время дня.  Описание этого метода см. в разделе [Определение возможности печати в заданное время суток](../../../../docs/framework/wpf/advanced/how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Чтобы проверить состояние задания печати с помощью флагов свойства <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A>, следует выполнить проверку состояния всех соответствующих флагов.  Стандартным способом просмотра, установлен ли один бит в наборе битовых флагов, является применение логической операции AND с набором флагов в качестве одного операнда и самого флага — в качестве другого.  Так как сам флаг имеет только одно битовое значение, результатом применения логического оператора AND является то, что в большинстве случаев устанавливается тот же самый бит.  Чтобы узнать, справедливо ли это, просто сравните результат применения логического оператора AND и значение самого флага.  Дополнительные сведения см. в разделах <xref:System.Printing.PrintJobStatus>, [Оператор & \(Справочник по C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) и <xref:System.FlagsAttribute>.  
  
 Для каждого атрибута, для которого установлен этот бит, в окне консоли выводится соответствующее уведомление, а в некоторых случаях также предлагаются способы реагирования.  \(Метод **HandlePausedJob**, который вызывается в случае приостановки задания или очереди, описывается ниже.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Чтобы проверить состояние задания печати с помощью отдельных свойств, следует считать соответствующие свойства и вывести уведомления и возможные способы реагирования для свойств со значениями `true` в окне консоли.  \(Метод **HandlePausedJob**, который вызывается в случае приостановки задания или очереди, описывается ниже.\)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Метод **HandlePausedJob** позволяет пользователю приложения удаленно возобновить приостановленные задания.  Поскольку приостановка очереди печати может быть вызвана необходимостью, при выполнении метода сначала отображается запрос на продолжение печати.  При выборе варианта «Y» вызывается метод <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=fullName>.  
  
 После этого отображается запрос на автоматическое возобновление задания, приостановленного независимо от очереди печати.  \(Сравните значения свойств <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=fullName> и <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=fullName>.\) При выборе варианта «Y» вызывается метод <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=fullName>. В противном случае вызывается метод <xref:System.Printing.PrintSystemJobInfo.Cancel%2A>.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## См. также  
 <xref:System.Printing.PrintJobStatus>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintQueue>   
 [Оператор & \(Справочник по C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)