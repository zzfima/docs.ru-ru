---
title: "Пул управляемых потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38032fccce1a8f6f7cbcb3bbd3d3f9d008a74141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="the-managed-thread-pool"></a>Пул управляемых потоков
Класс <xref:System.Threading.ThreadPool> обеспечивает приложение пулом рабочих потоков, управляемых системой, позволяя пользователю сосредоточиться на выполнении задач приложения, а не на управлении потоками. Если имеются небольшие задачи, которые требуют фоновой обработки, пул управляемых потоков — это самый простой способ воспользоваться преимуществами нескольких потоков. Например, начиная с версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] можно создавать объекты <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, выполняющие асинхронные задачи в потоках из пула потоков.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)] пропускная способность пула потоков значительно увеличилась в трех ключевых областях, которые считались узкими местами в предыдущих выпусках [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: постановка задач в очередь, диспетчеризация потоков в пуле и диспетчеризация потоков завершения ввода-вывода. Для применения этих функциональных возможностей приложение должно использовать [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] или более поздние версии.  
  
 Для фоновых задач, взаимодействующих с пользовательским интерфейсом, платформа .NET Framework версии 2.0 также предоставляет класс <xref:System.ComponentModel.BackgroundWorker>, который работает с помощью событий, возникающих в потоке пользовательского интерфейса.  
  
 Платформа .NET Framework использует потоки из пула потоков в различных целях, включая завершение асинхронного ввода-вывода, обратные вызовы таймера, зарегистрированные операции ожидания, асинхронные вызовы методов с использованием делегатов и подключения к сокетам <xref:System.Net>.  
  
## <a name="when-not-to-use-thread-pool-threads"></a>Когда не следует использовать потоки из пула потоков  
 Существует ряд сценариев, в которых следует создавать собственные потоки и управлять ими, а не использовать потоки из пула потоков.  
  
-   Необходим основной поток.  
  
-   Поток должен иметь определенный приоритет.  
  
-   Имеются задачи, которые приводят к блокировке потока на длительное время. Для пула потоков определено максимальное количество потоков, поэтому большое число заблокированных потоков в пуле может препятствовать запуску задач.  
  
-   Необходимо поместить потоки в однопотоковое подразделение. Все потоки <xref:System.Threading.ThreadPool> находятся в многопотоковом подразделении.  
  
-   Необходимо иметь постоянное удостоверение, сопоставленное с потоком, или назначить поток задаче.  
  
## <a name="thread-pool-characteristics"></a>Характеристики пула потоков  
 Потоки из пула потоков являются фоновыми. В разделе [основные и фоновые потоки](../../../docs/standard/threading/foreground-and-background-threads.md). Для каждого потока используется размер стека по умолчанию, поток запускается с приоритетом по умолчанию и находится в многопотоковом подразделении.  
  
 Для каждого процесса существует только один пул потоков.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Исключения в потоках из пула потоков  
 Необработанные исключения в потоках из пула потоков приводят к завершению процесса. Существует три исключения из этого правила.  
  
-   Исключение <xref:System.Threading.ThreadAbortException> создается в потоке пула потоков вследствие вызова <xref:System.Threading.Thread.Abort%2A>.  
  
-   Исключение <xref:System.AppDomainUnloadedException> создается в потоке пула потоков вследствие выгрузки домена приложения.  
  
-   Среда CLR или процесс ведущего приложения прерывает выполнение потока.  
  
 Дополнительные сведения см. в разделе [исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  В .NET Framework версии 1.0 и 1.1 среда CLR перехватывает необработанные исключения в потоках из пула потоков без вывода оповещения. Это может повредить состояние приложения и в итоге привести к его "зависанию", отладить которое может быть очень сложно.  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Максимальное количество потоков в пуле потоков  
 Количество операций, которое можно поместить в очередь пула потоков, ограничено только объемом памяти; однако пул потоков ограничивает количество потоков, которые могут быть одновременно активны в процессе. Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] размер по умолчанию пула потоков для процесса зависит от нескольких факторов, таких как размер виртуального адресного пространства. Процесс может вызвать метод <xref:System.Threading.ThreadPool.GetMaxThreads%2A> для определения количества потоков.  
  
 Вы можете управлять максимальным количеством потоков с помощью методов <xref:System.Threading.ThreadPool.GetMaxThreads%2A> и <xref:System.Threading.ThreadPool.SetMaxThreads%2A>.  
  
> [!NOTE]
>  В .NET Framework версии 1.0 и 1.1 размер пула потоков нельзя задать в управляемом коде. В коде, содержащем среду CLR, этот размер может задаваться с помощью объекта `CorSetMaxThreads`, определенного в mscoree.h.  
  
### <a name="thread-pool-minimums"></a>Минимальные значения пула потоков  
 Пул потоков предоставляет новые рабочие потоки или потоки завершения ввода-вывода по запросу, пока не будет достигнут заданный минимум для каждой категории. Для получения этих минимальных значений можно использовать метод <xref:System.Threading.ThreadPool.GetMinThreads%2A>.  
  
> [!NOTE]
>  Если потребность низкая, фактическое количество потоков из пула потоков может быть ниже минимальных значений.  
  
 При достижении минимума пул потоков может создавать дополнительные потоки или ожидать завершения некоторых задач. Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] пул потоков создает и уничтожает рабочие потоки в целях оптимизации пропускной способности, которая определяется как количество задач, завершаемых за единицу времени. Слишком малое количество потоков может препятствовать оптимальному использованию доступных ресурсов, тогда как слишком большое их количество может усиливать конкуренцию за ресурсы.  
  
> [!CAUTION]
>  Для увеличения минимального количества бездействующих потоков можно использовать метод <xref:System.Threading.ThreadPool.SetMinThreads%2A>. Однако необоснованное увеличение этих значений может привести к снижению производительности. Если одновременно запускается слишком много задач, все они могут выполняться слишком медленно. В большинстве случаев пул потоков работает наилучшим образом, если он использует собственный алгоритм выделения потоков.  
  
## <a name="skipping-security-checks"></a>Пропуск проверок безопасности  
 Пул потоков также предоставляет методы <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> и <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Используйте эти методы только в том случае, если вы уверены, что стек вызывающего объекта не важен для проверок безопасности, осуществляемых во время выполнения задачи в очереди. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>и <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> оба захвата стек вызывающего объекта, который объединяется со стеком потока из пула потоков, когда поток начинает выполнять задачу. Если требуется проверка безопасности, проверяется весь стек. Несмотря на обеспечение безопасности, такая проверка также влияет на производительность.  
  
## <a name="using-the-thread-pool"></a>Использование пула потоков  
 Начиная с версии [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], самым простым способом использования пула потоков является использование [библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md). По умолчанию такие типы параллельных библиотек, как <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, используют потоки из пула потоков для выполнения задач. Пул потоков также можно использовать путем вызова <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> из управляемого кода (или `CorQueueUserWorkItem` из неуправляемого кода) и передачи делегата <xref:System.Threading.WaitCallback>, представляющего метод, который выполняет задачу. Другим способом использования пула потоков является помещение в очередь рабочих элементов, которые имеют отношение к операции ожидания, с помощью метода <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> и передача дескриптора <xref:System.Threading.WaitHandle>, который вызывает метод, представленный делегатом <xref:System.Threading.WaitOrTimerCallback>, при получении сигнала или истечении времени ожидания. Потоки из пула потоков используются для вызова методов обратного вызова.  
  
## <a name="threadpool-examples"></a>Примеры ThreadPool  
 В примерах кода в этом разделе пул потоков демонстрируется путем использования класса <xref:System.Threading.Tasks.Task>, метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> и метода <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType>.  
  
-   [Выполнение асинхронных задач с помощью библиотеки параллельных задач](#TaskParallelLibrary)  
  
-   [Асинхронное выполнение кода с помощью QueueUserWorkItem](#ExecuteCodeWithQUWI)  
  
-   [Предоставление данных задачи методу QueueUserWorkItem](#TaskDataForQUWI)  
  
-   [Использование RegisterWaitForSingleObject](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a>Выполнение асинхронных задач с помощью библиотеки параллельных задач  
 В примере ниже показан способ создания и использования объекта <xref:System.Threading.Tasks.Task> путем вызова метода <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType>. Пример, использующий <xref:System.Threading.Tasks.Task%601> класса для возвращения значения из асинхронной задачи см. в разделе [как: возвращение значения из задачи](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a>Асинхронное выполнение кода с помощью QueueUserWorkItem  
 В примере ниже с помощью метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> в очередь помещается очень простая задача, представленная методом `ThreadProc`.  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a>Предоставление данных задачи методу QueueUserWorkItem  
 В примере ниже с помощью метода <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> в очередь помещается задача, а затем для нее предоставляются данные.  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a>Использование RegisterWaitForSingleObject  
 В примере ниже показаны некоторые возможности потоков:  
  
-   помещение задачи в очередь для выполнения с помощью потоков <xref:System.Threading.ThreadPool> с использованием метода <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A>;  
  
-   отправка задаче сигнала о выполнении с помощью <xref:System.Threading.AutoResetEvent>; В разделе [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
-   обработка тайм-аутов и сигналов с помощью делегата <xref:System.Threading.WaitOrTimerCallback>;  
  
-   отмена задачи в очереди с помощью <xref:System.Threading.RegisteredWaitHandle>.  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [Практическое руководство. Возвращение значения из задачи](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Потоки и работа с потоками](../../../docs/standard/threading/threads-and-threading.md)  
 [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [Таймеры](../../../docs/standard/threading/timers.md)
