---
title: "Практическое руководство. Определение возможности печати в заданное время суток | Microsoft Docs"
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
  - "задания печати, учет времени"
  - "очереди печати, учет времени"
  - "принтеры, доступность"
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Определение возможности печати в заданное время суток
Очереди печати не всегда доступны 24 часа в сутки.  У них есть свойства времени начала и окончания, установка которых делает очереди печати недоступными в определенные часы.  Эта возможность может быть использована, например, чтобы зарезервировать принтер для монопольного использования определенным отделом после 17.00.  Этому отделу необходимо иметь отличную от других отделов очередь обслуживания принтера.  Для других отделов очередь станет недоступной после 17.00, в то время как очередь для привилегированного отдела может быть доступна круглосуточно.  
  
 Кроме того, сами задания печати могут быть доступны для печати только в указанный промежуток времени.  
  
 Классы <xref:System.Printing.PrintQueue> и <xref:System.Printing.PrintSystemJobInfo>, представленные в [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], предоставляют средства для удаленной проверки возможности печати данного задания из данной очереди в текущий момент.  
  
## Пример  
 Представленный ниже пример является моделью, с помощью которой можно выявить проблемы с заданием печати.  
  
 Для этого типа функций существуют два основных действия, которые показаны ниже.  
  
1.  Считайте значения свойств <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> для <xref:System.Printing.PrintQueue>, чтобы определить, находится ли текущее время в интервале между ними.  
  
2.  Считайте значения свойств <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> и <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> для <xref:System.Printing.PrintSystemJobInfo>, чтобы определить, находится ли текущее время в интервале между ними.  
  
 Сложности возникают из\-за того, что эти свойства не являются объектами <xref:System.DateTime>.  Они являются объектами <xref:System.Int32>, представляющими время суток как число минут после полуночи.  Кроме того, под полночью подразумевается полночь не в текущем часовом поясе, а полночь по Гринвичу \(UTC\).  
  
 В первом примере кода представлен статический метод **ReportQueueAndJobAvailability**, которому передается <xref:System.Printing.PrintSystemJobInfo> и который вызывает вспомогательные методы для определения, можно ли напечатать задание в текущий момент, и если нет — время возможной печати.  Обратите внимание, что <xref:System.Printing.PrintQueue> не передается методу.  Это происходит потому, что <xref:System.Printing.PrintSystemJobInfo> содержит ссылку на очередь в своем свойстве <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A>.  
  
 Подчиненные методы включают перегруженный метод **ReportAvailabilityAtThisTime**, который может принимать в качестве параметра либо <xref:System.Printing.PrintQueue>, либо <xref:System.Printing.PrintSystemJobInfo>.  Также имеется **TimeConverter.ConvertToLocalHumanReadableTime**.  Все эти методы рассматриваются ниже.  
  
 Метод **ReportQueueAndJobAvailability** начинается с проверки доступности очереди или задания печати в текущий момент.  Если хотя бы одно из них недоступно, то проверяется доступность очереди.  Если она недоступна, то метод выдает отчет об этом факте и времени, когда очередь вновь станет доступной.  Затем проверяется задание и, в случае его недоступности, выводится следующий промежуток времени, когда оно может быть напечатано.  Наконец, метод сообщает ближайшее время, когда задание можно напечатать.  Это наиболее позднее время из двух следующих вариантов.  
  
-   Время, когда в очередь печати вновь будет доступна.  
  
-   Время, когда задание печати вновь будет доступно.  
  
 При сообщении времени суток также вызывается метод <xref:System.DateTime.ToShortTimeString%2A>, преобразующий выходные данные в формат года, месяца и дня.  Нельзя ограничить доступность очереди печати или задания печати конкретным годом, месяцем и днем.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 Два перегруженных метода **ReportAvailabilityAtThisTime** идентичны, за исключением передаваемого в них типа, поэтому ниже рассматривается только версия <xref:System.Printing.PrintQueue>.  
  
> [!NOTE]
>  Тот факт, что методы идентичны за исключением типа, вызывает вопрос, почему в примере не создается универсальный метод **ReportAvailabilityAtThisTime\<T\>**.  Причиной является то, что такой метод был бы ограничен классом значений свойств **StartTimeOfDay** и **UntilTimeOfDay**, которые вызывает метод, но универсальный метод может быть ограничен только одним классом, и единственным общим для <xref:System.Printing.PrintQueue> и <xref:System.Printing.PrintSystemJobInfo> классом в дереве наследования является <xref:System.Printing.PrintSystemObject>, который не имеет таких свойств.  
  
 Метод **ReportAvailabilityAtThisTime** \(представлен в следующем примере кода\) начинается с инициализации сигнальной переменной <xref:System.Boolean> в значение `true`.  Если очередь недоступна, значение будет изменено на `false`,.  
  
 Затем метод проверяет совпадение времени начала и завершения.  Если они идентичны, то очередь доступна всегда, поэтому метод возвращает `true`.  
  
 Если очередь все время не доступна, то метод использует статическое свойство <xref:System.DateTime.UtcNow%2A> для получения текущего времени в виде объекта <xref:System.DateTime>.  \(Локальное время не требуется, поскольку свойства <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> и <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> используют формат UTC\).  
  
 Однако эти два свойства не являются объектами <xref:System.DateTime>.  Они являются объектами <xref:System.Int32>, задающими время как число минут после полуночи в формате UTC.  Поэтому необходимо преобразовать объект <xref:System.DateTime> в минуты после полуночи.  После этого метод осуществляет проверку попадания текущего времени в интервал между началом и завершением очереди, устанавливает флаг в «false», если текущее время не принадлежит этому интервалу, и возвращает этот флаг.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 Метод **TimeConverter.ConvertToLocalHumanReadableTime** \(представлен в следующем примере кода\) не использует методы, которые используются с [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], поэтому изложение будет кратким.  Данный метод имеет задачу двойного преобразования. Он должен принимать число, выраженное числом минут после полуночи, и преобразовывать его в удобный для восприятия вид, а затем к местному времени.  Для этого сначала создается объект <xref:System.DateTime>, которому задается значение 00:00 часов по Гринвичу, и затем используется метод <xref:System.DateTime.AddMinutes%2A> для добавления минут, которые были переданы в метод.  При этом возвращается новый объект <xref:System.DateTime>, содержащий исходное время, которое было передано в метод.  Затем метод <xref:System.DateTime.ToLocalTime%2A> преобразует его к местному времени.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## См. также  
 <xref:System.DateTime>   
 <xref:System.Printing.PrintSystemJobInfo>   
 <xref:System.Printing.PrintQueue>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)