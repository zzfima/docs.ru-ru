---
title: Практическое руководство. Удаленный опрос состояний принтеров
ms.date: 03/30/2017
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
ms.openlocfilehash: 0a7756684d5a133fa9cb014f109d14e413223ea9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945228"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Практическое руководство. Удаленный опрос состояний принтеров
В средних и крупных компаниях могут возникнуть ситуации, когда из-за замятия или отсутствия бумаги либо по иным причинам не работают сразу несколько принтеров. Широкий набор свойств принтера, предоставляемых API Microsoft .NET Framework, предоставляет средства для быстрого опроса состояний принтеров.  
  
## <a name="example"></a>Пример  
 Ниже представлены основные этапы создания подобной служебной программы.  
  
1. Получите список всех серверов печати.  
  
2. Выполните циклический просмотр всех серверов, чтобы запросить их очереди печати.  
  
3. Для каждого сервера выполните циклический просмотр всех очередей сервера и прочтите каждое свойство, которое может указывать на то, что очередь в данный момент не работает.  
  
 Представленный ниже код представляет собой набор фрагментов. Для простоты в этом примере предполагается наличие списка серверов печати, разделенного символами перевода строки. `fileOfPrintServers` Переменная<xref:System.IO.StreamReader> является объектом для этого файла. Поскольку каждое имя сервера находится в отдельной строке, любой вызов <xref:System.IO.StreamReader.ReadLine%2A> получает имя следующего сервера и <xref:System.IO.StreamReader>перемещает курсор в начало следующей строки.  
  
 Во внешнем цикле код создает <xref:System.Printing.PrintServer> объект для последнего сервера печати и указывает, что приложение имеет права администратора на сервере.  
  
> [!NOTE]
> При наличии большого количества серверов можно повысить производительность с помощью <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> конструкторов, которые только инициализируют нужные свойства.  
  
 Затем в примере используется <xref:System.Printing.PrintServer.GetPrintQueues%2A> для создания коллекции всех очередей сервера и начинается их цикл. Этот внутренний цикл содержит структуру ветвления, соответствующую двум способам проверки состояния принтера:  
  
- Можно прочитать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства, имеющего тип <xref:System.Printing.PrintQueueStatus>.  
  
- Можно прочитать каждое соответствующее свойство <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, например, и. <xref:System.Printing.PrintQueue.IsPaperJammed%2A>  
  
 В этом примере демонстрируются оба метода, поэтому пользователю ранее было предложено, какой метод использовать, и ответил "y", если ему нужно использовать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства. Ниже представлены подробные сведения об этих двух методах.  
  
 В конечном итоге результаты предоставляются пользователю.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Чтобы проверить состояние принтера с помощью флагов <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства, необходимо проверить каждый соответствующий флаг, чтобы проверить, задан ли он. Обычно определить, задан ли один бит в наборе битовых флагов, позволяет логическая операция И с набором флагов в качестве одной операнды и самим флагом в качестве второй. Поскольку сам флаг имеет только один набор битов, результатом логической операции И может стать максимум установка самого бита. Чтобы определить, установлен ли этот бит, просто сравните результат логической операции И с самим флагом. Дополнительные сведения см. в <xref:System.Printing.PrintQueueStatus>разделе, [оператор & (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)и. <xref:System.FlagsAttribute>  
  
 Для каждого атрибута с установленным битом код добавляет уведомление в итоговый отчет, который будет представлен пользователю. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Чтобы проверить состояние принтера с помощью каждого свойства, просто прочтите каждое свойство и добавьте примечание, если какое-либо свойство имеет значение `true`, в итоговый отчет для пользователя. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Метод **ReportAvailabilityAtThisTime** позволяет определить наличие очереди в текущее время суток.  
  
 Метод не будет выполнять никаких действий, <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> если <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства и равны; так как в этом случае принтер доступен постоянно. Если они различаются, метод получает текущее время, которое затем должно быть преобразовано в общее число минут после полуночи, так <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> как <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства и <xref:System.Int32>представляют собой минуты после полуночи, а не <xref:System.DateTime> объект. В конечном итоге метод проверяет, находится ли текущее время в промежутке между временем начала и окончания.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [Оператор & (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
