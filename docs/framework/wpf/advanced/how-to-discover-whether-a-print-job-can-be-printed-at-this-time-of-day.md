---
title: "Практическое руководство. Определение возможности печати в заданное время суток"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ac89b8dce67c95c78a5dd46e591d84730a68346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Практическое руководство. Определение возможности печати в заданное время суток
Очереди печати не всегда доступны на 24 часа в сутки. Они имеют свойства времени начала и окончания, можно задать, чтобы сделать недоступным в определенное время дня. Эта функция используется, например, чтобы зарезервировать принтер для монопольного использования определенным отделом после 17: 00. Этот отдел будет иметь другой очереди обслуживания принтера от других отделов используйте. Будет иметь значение в очередь для других отделов станет недоступной после 17: 00, пока очередь для привилегированного отдела может быть задано равным доступны в любое время.  
  
 Кроме того задания печати, сами можно задать для печати только в указанный промежуток времени.  
  
 <xref:System.Printing.PrintQueue> И <xref:System.Printing.PrintSystemJobInfo> классы представлены в [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] из [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] предоставляют средства для удаленной проверки, является ли данное задание печати можно напечатать из данной очереди в настоящее время.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере — это пример, можно диагностировать проблемы с задание печати.  
  
 Существует два основных действия для этого вида функции следующим образом.  
  
1.  Чтение <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства <xref:System.Printing.PrintQueue> , чтобы определить, является ли текущее время между ними.  
  
2.  Чтение <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> и <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> свойства <xref:System.Printing.PrintSystemJobInfo> , чтобы определить, является ли текущее время между ними.  
  
 Сложности возникают из-за того, эти свойства не являются <xref:System.DateTime> объектов. Вместо этого они являются <xref:System.Int32> объектами, представляющими время суток как число минут, прошедших с полуночи. Кроме того это не полуночи в текущем часовом поясе, но в полночь по времени UTC (время по Гринвичу).  
  
 В первом примере кода представлен статический метод **ReportQueueAndJobAvailability**, который передается <xref:System.Printing.PrintSystemJobInfo> и вызывает вспомогательные методы для определения, может ли задание печати в настоящее время и, если нет, когда можно напечатать. Обратите внимание, что <xref:System.Printing.PrintQueue> не передается в метод. Это вызвано <xref:System.Printing.PrintSystemJobInfo> включает ссылку на очередь в его <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> свойство.  
  
 Перечислены перегруженные методы, подчиненных **ReportAvailabilityAtThisTime** метод, который может принимать <xref:System.Printing.PrintQueue> или <xref:System.Printing.PrintSystemJobInfo> как параметр. Имеется также **TimeConverter.ConvertToLocalHumanReadableTime**. Все эти методы описаны ниже.  
  
 **ReportQueueAndJobAvailability** метода начинается с проверки, если очередь или задание печати недоступна в данный момент. Если любое из них недоступен, затем проверяется на предмет очередь недоступной. Если она недоступна, метод сообщает этот факт и время, когда очередь снова станут доступны. Затем он проверяет, задания и если он недоступен, сообщает в следующий раз span при его при печати. Наконец метод сообщает самое раннее время, когда задание можно напечатать. Это более поздним два раза, приведенному ниже.  
  
-   Время, когда очередь печати Далее доступен.  
  
-   Время, когда задание печати Далее будет доступен.  
  
 При сообщении времени суток, <xref:System.DateTime.ToShortTimeString%2A> метод также вызывается этот метод отменяет года, месяца и дня из выходных данных. Нельзя ограничить доступность очереди печати или задания печати для определенного года, месяцев или дней.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Два перегрузки **ReportAvailabilityAtThisTime** метод идентичны за исключением типа, переданный в них, таким образом, только <xref:System.Printing.PrintQueue> версии представлена ниже.  
  
> [!NOTE]
>  Тот факт, что методы идентичны за исключением типа, вызывает вопрос, почему в примере не создается универсальный метод **ReportAvailabilityAtThisTime\<T >**. Причина заключается в том, что этот метод будет иметь должны быть ограничены классом, имеющим **StartTimeOfDay** и **UntilTimeOfDay** только можно ограничить свойства, которые вызывает метод, но универсальный метод один класс и единственным общим для обоих <xref:System.Printing.PrintQueue> и <xref:System.Printing.PrintSystemJobInfo> в цепочке наследования дерево является <xref:System.Printing.PrintSystemObject> которого не имеет таких свойств.  
  
 **ReportAvailabilityAtThisTime** метод (представленных в следующем примере кода) начинается путем инициализации <xref:System.Boolean> sentinel переменной `true`. Оно будет сброшено в `false`, если очередь не доступна.  
  
 Затем метод проверяет начала а «до «раз идентичны. Если это так, очередь доступна всегда, поэтому метод возвращает `true`.  
  
 Если очередь не доступны все время, метод использует статический <xref:System.DateTime.UtcNow%2A> свойства, чтобы получить текущее время как <xref:System.DateTime> объект. (Так как не требуется местное время <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> используют формат времени в формате UTC.)  
  
 Тем не менее, эти два свойства не являются <xref:System.DateTime> объектов. Они являются <xref:System.Int32>задающими время как число минут после полуночи в формате UTC. Поэтому необходимо преобразовать нашей <xref:System.DateTime> объекта в минутах после полуночи. Когда это будет сделано, метод просто проверяет ли «сейчас» между начала очереди, а также время наборы не попадает в два раза флаг в значение false, если «сейчас» и возвращает этот флаг «до».  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 **TimeConverter.ConvertToLocalHumanReadableTime** (представленных в следующем примере кода) метод не использует методы, появившиеся в [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], поэтому краткое описание. Этот метод имеет задачу двойного преобразования: он должен принимать целое число минут после полуночи выражения и преобразовать его в удобное для восприятия времени, и его необходимо преобразовать в местное время. Это делается путем первоначального создания <xref:System.DateTime> объекта, устанавливается значение полуночи в формате UTC, а затем использует <xref:System.DateTime.AddMinutes%2A> метод, чтобы добавить минут, которые были переданы в метод. Возвращает новый <xref:System.DateTime> содержащий исходное время, которое было передано в метод. <xref:System.DateTime.ToLocalTime%2A> Метод затем преобразует это в местное время.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)
