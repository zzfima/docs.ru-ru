---
title: Практическое руководство. Удаленный опрос состояний принтеров
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3d0faedbe8ce3394fb888a6509ece1441f0a353a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Практическое руководство. Удаленный опрос состояний принтеров
В средних и крупных компаниях могут возникнуть ситуации, когда из-за замятия или отсутствия бумаги либо по иным причинам не работают сразу несколько принтеров. Широкий набор свойств принтера в [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] платформы Microsoft .NET Framework предоставляют средства для выполнения быстрого опроса состояния принтеров.  
  
## <a name="example"></a>Пример  
 Ниже представлены основные этапы создания подобной служебной программы.  
  
1.  Получите список всех серверов печати.  
  
2.  Выполните циклический просмотр всех серверов, чтобы запросить их очереди печати.  
  
3.  Для каждого сервера выполните циклический просмотр всех очередей сервера и прочтите каждое свойство, которое может указывать на то, что очередь в данный момент не работает.  
  
 Представленный ниже код представляет собой набор фрагментов. Для простоты в этом примере предполагается наличие списка серверов печати, разделенного символами перевода строки. Переменная `fileOfPrintServers` — <xref:System.IO.StreamReader> этого файла. Поскольку каждое имя сервера в отдельной строке, любой вызов метода <xref:System.IO.StreamReader.ReadLine%2A> возвращает имя следующего сервера и перемещает <xref:System.IO.StreamReader>на курсор в начало следующей строки.  
  
 Во внешнем цикле в коде создается <xref:System.Printing.PrintServer> объекта для последнего сервера печати и указывается, что приложение должно обладать правами администратора на сервере.  
  
> [!NOTE]
>  При наличии большого количества серверов, можно повысить производительность с помощью <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> конструкторы, которые инициализируют только необходимые свойства будут нужны.  
  
 Затем в примере используется <xref:System.Printing.PrintServer.GetPrintQueues%2A> для создания коллекции всех сервера, помещает в очередь и начинается проход по ним. Этот внутренний цикл содержит структуру ветвления, соответствующую двум способам проверки состояния принтера:  
  
-   Можно прочитать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойство с типом <xref:System.Printing.PrintQueueStatus>.  
  
-   Можно прочитать каждого соответствующего свойства, такие как <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, и <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 В этом примере демонстрируются оба метода, чтобы пользователь был ранее какой метод использовать и выбрать ответ «y», если требуется использовать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойство. Ниже представлены подробные сведения об этих двух методах.  
  
 В конечном итоге результаты предоставляются пользователю.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Чтобы проверить состояние принтера с помощью флагов <xref:System.Printing.PrintQueue.QueueStatus%2A> свойство, проверьте каждого соответствующего флага имеет значение. Обычно определить, задан ли один бит в наборе битовых флагов, позволяет логическая операция И с набором флагов в качестве одной операнды и самим флагом в качестве второй. Поскольку сам флаг имеет только один набор битов, результатом логической операции И может стать максимум установка самого бита. Чтобы определить, установлен ли этот бит, просто сравните результат логической операции И с самим флагом. Дополнительные сведения см. в разделе <xref:System.Printing.PrintQueueStatus>, [& оператор (Справочник по C#)](~/docs/csharp/language-reference/operators/and-operator.md), и <xref:System.FlagsAttribute>.  
  
 Для каждого атрибута с установленным битом код добавляет уведомление в итоговый отчет, который будет представлен пользователю. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Чтобы проверить состояние принтера с помощью каждого свойства, просто прочтите каждое свойство и добавьте примечание, если какое-либо свойство имеет значение `true`, в итоговый отчет для пользователя. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Метод **ReportAvailabilityAtThisTime** позволяет определить наличие очереди в текущее время суток.  
  
 Метод не выполняет никаких действий при <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства равны, поскольку в этом случае принтер доступен в любое время. Если они не совпадают, метод возвращает текущее время, которое затем должно быть преобразовано в количество минут, прошедших после полуночи, так как <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства <xref:System.Int32>, представляющих минуты после полуночи, не <xref:System.DateTime> объекты. В конечном итоге метод проверяет, находится ли текущее время в промежутке между временем начала и окончания.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>См. также  
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
 [& Оператор (Справочник по C#)](~/docs/csharp/language-reference/operators/and-operator.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)
