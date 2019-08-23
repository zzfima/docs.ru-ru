---
title: Практическое руководство. Определение возможности печати в заданное время суток
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
ms.openlocfilehash: 859dc75169e443d07361951692a428507886fa2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947800"
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>Практическое руководство. Определение возможности печати в заданное время суток
Очереди печати не всегда доступны в течение 24 часов в день. Они имеют свойства времени начала и окончания, которые можно установить, чтобы сделать их недоступными в определенное время суток. С помощью этой функции можно, например, зарезервировать принтер на монопольное использование определенного отдела после 5 часов. Этот отдел будет иметь другую очередь, которая обслуживает принтер по сравнению с использованием других отделов. Очередь для других отделов будет настроена как недоступная после 5 часов, а очередь для предпочитаемого отдела может быть доступна в любое время.  
  
 Кроме того, сами задания печати могут быть настроены на печать только в течение определенного промежутка времени.  
  
 Классы <xref:System.Printing.PrintQueue> и<xref:System.Printing.PrintSystemJobInfo> , предоставляемые в API-интерфейсах Microsoft .NET Framework, предоставляют средства для удаленной проверки того, может ли данное задание печати печататься в данной очереди в текущий момент времени.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, который может диагностировать проблемы с заданием печати.  
  
 Существует два основных шага для этого типа функции, как показано ниже.  
  
1. Прочитайте свойства <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> <xref:System.Printing.PrintQueue> и объекта, чтобы определить, находится ли между ними текущее время. <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>  
  
2. Прочитайте свойства <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> <xref:System.Printing.PrintSystemJobInfo> и объекта, чтобы определить, находится ли между ними текущее время. <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A>  
  
 Но сложности возникают из того факта, что эти свойства <xref:System.DateTime> не являются объектами. Вместо этого они <xref:System.Int32> представляют собой объекты, которые представляют время суток в виде числа минут с полуночи. Более того, это не полночь в текущем часовом поясе, но полночь UTC (время в формате UTC).  
  
 В первом примере кода представлен статический метод **репорткуеуеанджобаваилабилити**, который передается <xref:System.Printing.PrintSystemJobInfo> и вызывает вспомогательные методы, чтобы определить, может ли задание печататься в текущее время, и, если нет, когда оно может печататься. Обратите внимание <xref:System.Printing.PrintQueue> , что объект не передается в метод. Это обусловлено тем <xref:System.Printing.PrintSystemJobInfo> , что включает ссылку на очередь в ее <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> свойстве.  
  
 Подчиненные методы включают перегруженный метод **ReportAvailabilityAtThisTime** , который в <xref:System.Printing.PrintQueue> <xref:System.Printing.PrintSystemJobInfo> качестве параметра может принимать значение или. Существует также **тимеконвертер. конверттолокалхуманреадаблетиме**. Ниже описаны все эти методы.  
  
 Метод **репорткуеуеанджобаваилабилити** начинается с проверки недоступности очереди или задания печати в данный момент. Если один из них недоступен, он проверяет, недоступна ли очередь. Если он недоступен, метод сообщает об этом факте и о времени, когда очередь снова станет доступной. Затем он проверяет задание и, если он недоступен, он сообщает о следующем интервале времени, когда он может выполнить печать. Наконец, метод сообщает о том, что задание может быть напечатано раньше. Это более позднее из следующих двух раз.  
  
- Время, когда очередь печати становится следующей доступной.  
  
- Время следующего доступности задания печати.  
  
 При отправке отчетов о времени суток <xref:System.DateTime.ToShortTimeString%2A> метод также вызывается, так как этот метод подавляет годы, месяцы и дни из выходных данных. Нельзя ограничить доступность очереди печати или задания печати определенными годами, месяцами или днями.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Две перегрузки метода **ReportAvailabilityAtThisTime** идентичны, за исключением передаваемого им типа, поэтому ниже приведена только <xref:System.Printing.PrintQueue> версия.  
  
> [!NOTE]
> Тот факт, что методы идентичны, за исключением типа, вызывает вопрос о том, почему в примере не создается универсальный **метод\<ReportAvailabilityAtThisTime T >** . Причина заключается в том, что такой метод должен быть ограничен классом, имеющим свойства **StartTimeOfDay** и **UntilTimeOfDay** , которые вызывает метод, но универсальный метод может быть ограничен только одним классом и классом, общим для обоих. вдеревенаследованиянеттакихсвойств.<xref:System.Printing.PrintSystemJobInfo> <xref:System.Printing.PrintQueue> <xref:System.Printing.PrintSystemObject>  
  
 Метод **ReportAvailabilityAtThisTime** (представленный в примере кода ниже) начинается с инициализации <xref:System.Boolean> переменной Sentinel в. `true` Если очередь недоступна `false`, она будет сброшена на.  
  
 Затем метод проверяет, совпадают ли значения времени начала и "пока". Если они есть, то очередь всегда доступна, поэтому метод возвращает `true`.  
  
 Если очередь недоступна все время, метод использует статическое <xref:System.DateTime.UtcNow%2A> свойство для получения текущего времени в <xref:System.DateTime> виде объекта. (Не требуется местное время, так как <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> свойства и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> находятся в формате UTC.)  
  
 Однако эти два свойства не <xref:System.DateTime> являются объектами. Они представляют <xref:System.Int32>время в виде числа минут после полуночи в формате UTC. Поэтому нам нужно преобразовать наш <xref:System.DateTime> объект в минуты – после полуночи. После этого метод просто проверяет, находится ли "сейчас" между началом и временем ожидания очереди, устанавливает для Sentinel значение false, если "Now" не находится между двумя значениями времени, и возвращает метку.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Метод **тимеконвертер. конверттолокалхуманреадаблетиме** (представленный в примере кода ниже) не использует методы, представленные в Microsoft .NET Framework, поэтому обсуждение является кратким. Метод имеет задачу двойного преобразования: она должна принимать целочисленное значение минут после полуночи и преобразовывать его в удобное для чтения время и преобразовывать его в местное время. Для этого сначала создается <xref:System.DateTime> объект, для которого установлено значение полуночи в формате UTC, а затем <xref:System.DateTime.AddMinutes%2A> метод используется для добавления минут, переданных в метод. При этом возвращается новое <xref:System.DateTime> выражение, обозначающее исходное время, которое было передано в метод. Затем <xref:System.DateTime.ToLocalTime%2A> метод преобразует его в местное время.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>См. также

- <xref:System.DateTime>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.Printing.PrintQueue>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
