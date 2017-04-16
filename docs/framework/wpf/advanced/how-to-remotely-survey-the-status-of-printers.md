---
title: "Практическое руководство. Удаленный опрос состояний принтеров | Microsoft Docs"
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
  - "состояние принтера, удаленный опрос"
  - "удаленный опрос состояния принтеров"
  - "состояние, принтеры, удаленный опрос"
  - "удаленный опрос состояния принтеров"
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Удаленный опрос состояний принтеров
В любой момент времени в средних и крупных компаниях могут существовать несколько принтеров, не работающих из\-за замятия бумаги, отсутствия бумаги или каких\-то других проблемных ситуаций.  Широкий набор свойств принтера, предоставленных в интерфейсах [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] среды [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], предоставляет средства для выполнения быстрого опроса состояния принтеров.  
  
## Пример  
 Ниже приведены основные этапы по созданию служебной программы такого рода.  
  
1.  Получите список всех серверов печати.  
  
2.  Выполните цикл опроса серверов об их очередях печати.  
  
3.  В каждом проходе цикла через сервер просмотрите все очереди сервера и прочтите каждое свойство, которое может указывать на то, что очередь в данный момент не функционирует.  
  
 Приведенный ниже код представляет собой набор фрагментов кода.  Для простоты предполагается, что существует список серверов печати с разделителями CRLF.  Переменная `fileOfPrintServers` является объектом <xref:System.IO.StreamReader> этого файла.  Поскольку каждое имя сервера размещается в отдельной строке, любой вызов метода <xref:System.IO.StreamReader.ReadLine%2A> возвращает имя следующего сервера и перемещает курсор <xref:System.IO.StreamReader> в начало следующей строки.  
  
 Во внешнем цикле в коде создается объект <xref:System.Printing.PrintServer> для последнего сервера печати и указывается, что приложение должно обладать правами администратора сервера.  
  
> [!NOTE]
>  При наличии большого количества серверов можно повысить производительность с помощью конструкторов [PrintServer\(String, String\<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29>, которые инициализируют только необходимые свойства.  
  
 В примере затем используется метод <xref:System.Printing.PrintServer.GetPrintQueues%2A> для создания коллекции всех очередей сервера и начинается проход по ним.  Внутренний цикл содержит структуру перехода, соответствующую двум способам проверки состояния принтера:  
  
-   можно прочесть флаги свойства <xref:System.Printing.PrintQueue.QueueStatus%2A> типа <xref:System.Printing.PrintQueueStatus>;  
  
-   можно прочесть каждое соответствующее свойство, например <xref:System.Printing.PrintQueue.IsOutOfPaper%2A> и <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 В этом примере демонстрируются оба метода, так что пользователь имеет возможность заранее выбрать, какой метод следует использовать, и выбрать ответ «Y», если требуется использовать флаги свойства <xref:System.Printing.PrintQueue.QueueStatus%2A>.  Ниже приведены сведения об этих двух методах.  
  
 Наконец, результаты предоставляются пользователю.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Чтобы проверить состояние принтера с помощью флагов свойства <xref:System.Printing.PrintQueue.QueueStatus%2A>, выполняется проверка установки каждого соответствующего флага.  Стандартным способом просмотра, установлен ли один бит в наборе битовых флагов, является применение логической операции AND с набором флагов в качестве одного операнда и самого флага — в качестве другого.  Так как сам флаг имеет только одно битовое значение, результатом применения логического оператора AND является то, что в большинстве случаев устанавливается тот же самый бит.  Чтобы узнать, справедливо ли это, просто сравните результат применения логического оператора AND и значение самого флага.  Дополнительные сведения см. в разделах <xref:System.Printing.PrintQueueStatus>, [Оператор & \(Справочник по C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md) и <xref:System.FlagsAttribute>.  
  
 Для каждого атрибута, для которого задано битовое значение, в коде добавляется уведомление для окончательного отчета, который будет предоставлен пользователю.  \(Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описан ниже.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Чтобы проверить состояние принтера с помощью каждого свойства, необходимо прочесть каждое свойство и добавить уведомление в окончательный отчет, который будет предоставлен пользователю, если значение свойства — `true`.  \(Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описан ниже.\)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Метод **ReportAvailabilityAtThisTime** создан для того, чтобы при необходимости определить, доступна ли очередь в текущий момент времени.  
  
 Метод не выполняет действий, если свойства <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> равны; так как в этом случае принтер доступен в любое время.  Если они отличаются, метод получает значение текущего времени, которое затем должно быть преобразовано в количество минут, прошедших после полуночи, потому что свойства <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> являются типами <xref:System.Int32>, представляющими минуты после полуночи, а не объектами <xref:System.DateTime>.  Наконец, метод проверяет, попадает ли текущее время в период между временем начала и «до тех пор, пока».  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## См. также  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>   
 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>   
 <xref:System.DateTime>   
 <xref:System.Printing.PrintQueueStatus>   
 <xref:System.FlagsAttribute>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 [Оператор & \(Справочник по C\#\)](../Topic/&%20Operator%20\(C%23%20Reference\).md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)