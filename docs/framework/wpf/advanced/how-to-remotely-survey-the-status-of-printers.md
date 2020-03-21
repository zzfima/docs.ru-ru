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
ms.openlocfilehash: 859ccb703c6c54c66d6ea7b433c67d156627e25b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187042"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>Практическое руководство. Удаленный опрос состояний принтеров
В средних и крупных компаниях могут возникнуть ситуации, когда из-за замятия или отсутствия бумаги либо по иным причинам не работают сразу несколько принтеров. Богатый набор свойств принтеров, выставленных в AI Microsoft .NET Framework, предоставляет средства для проведения быстрого обследования состояний принтеров.  
  
## <a name="example"></a>Пример  
 Ниже представлены основные этапы создания подобной служебной программы.  
  
1. Получите список всех серверов печати.  
  
2. Выполните циклический просмотр всех серверов, чтобы запросить их очереди печати.  
  
3. Для каждого сервера выполните циклический просмотр всех очередей сервера и прочтите каждое свойство, которое может указывать на то, что очередь в данный момент не работает.  
  
 Представленный ниже код представляет собой набор фрагментов. Для простоты в этом примере предполагается наличие списка серверов печати, разделенного символами перевода строки. Переменная `fileOfPrintServers` является <xref:System.IO.StreamReader> объектом для этого файла. Так как каждое имя сервера находится <xref:System.IO.StreamReader.ReadLine%2A> на своей собственной линии, любой вызов получает имя следующего сервера и перемещает курсор <xref:System.IO.StreamReader>'ы к началу следующей строки.  
  
 В пределах внешнего цикла <xref:System.Printing.PrintServer> код создает объект для последнего сервера печати и указывает, что приложение должно иметь административные права на сервер.  
  
> [!NOTE]
> Если серверов много, можно повысить производительность, <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> используя конструкторы, которые только инициализируют свойства, которые вам понадобятся.  
  
 Затем пример <xref:System.Printing.PrintServer.GetPrintQueues%2A> используется для создания коллекции всех очередей сервера и начинает циклировать через них. Этот внутренний цикл содержит структуру ветвления, соответствующую двум способам проверки состояния принтера:  
  
- Вы можете прочитать <xref:System.Printing.PrintQueue.QueueStatus%2A> флаги собственности, которая имеет тип. <xref:System.Printing.PrintQueueStatus>  
  
- Вы можете прочитать каждое соответствующее свойство, такие как <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, и <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.  
  
 Этот пример демонстрирует оба метода, поэтому пользователю ранее было предложено, какой метод использовать, и <xref:System.Printing.PrintQueue.QueueStatus%2A> ответили "y", если они хотят использовать флаги свойства. Ниже представлены подробные сведения об этих двух методах.  
  
 В конечном итоге результаты предоставляются пользователю.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 Чтобы проверить состояние принтера <xref:System.Printing.PrintQueue.QueueStatus%2A> с помощью флагов свойства, вы проверяете каждый соответствующий флаг, чтобы увидеть, если он установлен. Обычно определить, задан ли один бит в наборе битовых флагов, позволяет логическая операция И с набором флагов в качестве одной операнды и самим флагом в качестве второй. Поскольку сам флаг имеет только один набор битов, результатом логической операции И может стать максимум установка самого бита. Чтобы определить, установлен ли этот бит, просто сравните результат логической операции И с самим флагом. Для получения дополнительной <xref:System.Printing.PrintQueueStatus>информации см.,& <xref:System.FlagsAttribute> [оператором (ссылка на СЗ)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)и .  
  
 Для каждого атрибута с установленным битом код добавляет уведомление в итоговый отчет, который будет представлен пользователю. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 Чтобы проверить состояние принтера с помощью каждого свойства, просто прочтите каждое свойство и добавьте примечание, если какое-либо свойство имеет значение `true`, в итоговый отчет для пользователя. (Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 Метод **ReportAvailabilityAtThisTime** позволяет определить наличие очереди в текущее время суток.  
  
 Метод ничего не <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> сделает, если свойства равны; <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> потому что в этом случае принтер доступен в любое время. Если они отличаются, метод получает текущее время, которое затем должно <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> быть <xref:System.Int32>преобразовано в общую минуту <xref:System.DateTime> после полуночи, потому что и свойства s представляющих минут после полуночи, а не объекты. В конечном итоге метод проверяет, находится ли текущее время в промежутке между временем начала и окончания.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>См. также раздел

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
- [Оператор& (Справка)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
