---
title: Практическое руководство. Диагностика проблем при выполнении заданий печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- troubleshooting print job problems [WPF]
- print jobs [WPF], troubleshooting
- print jobs [WPF], diagnosing problems
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
ms.openlocfilehash: 15de5d9ec8dc4016753b9d4cbed6fb0c64571774
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186044"
---
# <a name="how-to-diagnose-problematic-print-job"></a>Практическое руководство. Диагностика проблем при выполнении заданий печати
Администраторы сетей часто получают от пользователей жалобы на то, что задания печати не выполняются или выполняются слишком медленно. Богатый набор свойств заданий печати, выставленных в AA, Майкрософт .NET Framework, обеспечивает средства для проведения быстрой удаленной диагностики заданий печати.  
  
## <a name="example"></a>Пример  
 Ниже представлены основные этапы создания подобной служебной программы.  
  
1. Определите, на какое задание печати жалуется пользователь. Части пользователи не могут указать его точно. Они могут не знать имена серверов печати или принтеров. Они могут описать местоположение принтера в другой терминологии, <xref:System.Printing.PrintQueue.Location%2A> чем было использовано при настройке его свойства. В связи с этим будет полезно составить список задач, отправленных пользователем на данный момент. Если их несколько, определить, какое именно задание вызывает проблемы, позволит взаимодействие между пользователем и системным администратором печати. Порядок действий при этом следующий:  
  
    1. Получите список всех серверов печати.  
  
    2. Выполните циклический просмотр всех серверов, чтобы запросить их очереди печати.  
  
    3. Для каждого сервера выполните циклический просмотр всех очередей сервера, чтобы запросить их задания.  
  
    4. Для каждого цикла очереди выполните циклический просмотр ее заданий и соберите идентификационные данные заданий, отправленных подавшим жалобу пользователем.  
  
2. Обнаружив проблемное задание, изучите соответствующие свойства, чтобы узнать, в чем может быть проблема. Например, определите, находится ли задание в состоянии ошибки и не отключился ли обслуживающий очередь принтер от сети перед печатью задания.  
  
 Приведенный ниже код представляет собой последовательность примеров кода. Код в первом примере кода содержит циклический просмотр очередей печати. (Шаг 1c выше.) Переменная `myPrintQueues` — <xref:System.Printing.PrintQueueCollection> объект для текущего сервера печати.  
  
 Пример кода начинается с обновления текущего <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType>объекта очереди печати с помощью . Это гарантирует, что свойства объекта точно отображают состояние физического принтера, который он представляет. Затем приложение получает коллекцию заданий печати, <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>наданных в настоящее время в очереди печати с помощью .  
  
 Далее приложение циклов <xref:System.Printing.PrintSystemJobInfo> через коллекцию <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> и сравнивает каждое свойство с псевдонимом жалующегося пользователя. Если они совпадают, приложение добавляет идентификационные сведения о задании в предоставляемую строку. (Переменные `userName` и `jobList` инициализируются в приложении на более раннем этапе.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 В следующем примере кода выбирается приложение с шага 2. (См. выше.) Проблематичное задание было определено, и приложение подсказывает информацию, которая будет идентифицировать ее. Из этой информации <xref:System.Printing.PrintQueue>он <xref:System.Printing.PrintSystemJobInfo> создает, <xref:System.Printing.PrintServer>и объекты.  
  
 На этом этапе приложение содержит структуру ветвления, соответствующую двум способам проверки состояния заданий печати:  
  
- Вы можете прочитать <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> флаги собственности, которая имеет тип. <xref:System.Printing.PrintJobStatus>  
  
- Вы можете прочитать каждое соответствующее свойство, такие как <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> и <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>.  
  
 Этот пример демонстрирует оба метода, поэтому пользователю ранее было предложено, какой метод использовать, и <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> ответили на запрос "Y", если они хотят использовать флаги свойства. Ниже представлены подробные сведения об этих двух методах. Наконец, для создания отчетов о возможности печати соответствующего задания в это время суток в приложении используется метод под названием **ReportQueueAndJobAvailability**. Этот метод обсуждается в разделе [Практическое руководство. Определение возможности печати в заданное время суток](how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Чтобы проверить статус задания печати <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> с помощью флагов свойства, вы проверяете каждый соответствующий флаг, чтобы увидеть, если он установлен. Обычно определить, задан ли один бит в наборе битовых флагов, позволяет логическая операция И с набором флагов в качестве одной операнды и самим флагом в качестве второй. Поскольку сам флаг имеет только один набор битов, результатом логической операции И может стать максимум установка самого бита. Чтобы определить, установлен ли этот бит, просто сравните результат логической операции И с самим флагом. Для получения дополнительной <xref:System.Printing.PrintJobStatus>информации см.,& <xref:System.FlagsAttribute> [оператором (ссылка на СЗ)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)и .  
  
 Для каждого атрибута с заданным битом код передает соответствующие данные на экран консоли и иногда предлагает способы реагирования. (Метод **HandlePausedJob**, который вызывается в случае приостановки задания или очереди, описывается ниже.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Чтобы проверить состояние задания печати с помощью отдельных свойств, просто прочтите каждое свойство и, если свойство имеет значение `true`, передайте данные на экран консоли и по возможности предложите способ реагирования. (Метод **HandlePausedJob**, который вызывается в случае приостановки задания или очереди, описывается ниже.)  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 Метод **HandlePausedJob** позволяет пользователю приложения удаленно возобновлять приостановленные задания. Поскольку приостановка очереди печати может быть связана именно с этим, метод начинается с запроса решения пользователя о его возобновлении. Если ответ "Y", то <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> метод называется.  
  
 Затем пользователю предлагается решить, следует ли возобновить само задание печати (на случай, если оно было приостановлено независимо от очереди печати). (Сравните <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType>и .) Если ответ "Y", <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> то называется; в <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> противном случае называется.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [Оператор& (Справка)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
