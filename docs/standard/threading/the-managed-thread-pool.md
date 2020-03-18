---
title: Пул управляемых потоков
description: Сведения о пуле потоков .NET, обеспечивающем фоновые потоки рабочих процессов
ms.date: 08/02/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- thread pooling [.NET]
- thread pools [.NET]
- threading [.NET], thread pool
- threading [.NET], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
ms.openlocfilehash: 2671ce7c9721b15de8a3805da27040e973a62804
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79398559"
---
# <a name="the-managed-thread-pool"></a>Пул управляемых потоков

Класс <xref:System.Threading.ThreadPool?displayProperty=nameWithType> обеспечивает приложение пулом рабочих потоков, управляемых системой, позволяя пользователю сосредоточиться на выполнении задач приложения, а не на управлении потоками. Если имеются небольшие задачи, которые требуют фоновой обработки, пул управляемых потоков — это самый простой способ воспользоваться преимуществами нескольких потоков. В Framework 4 и более поздних версиях использовать пул потоков стало значительно проще, так как вы можете создавать объекты <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, которые выполняют в потоках пула асинхронные задачи.  
  
Платформа .NET использует потоки из пула в различных целях, в том числе для операций [библиотеки параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md), асинхронного ввода-вывода, обратных вызовов [таймера](timers.md), регистрируемых операций ожидания, асинхронного вызова методов с использованием делегатов и для подключения к сокетам <xref:System.Net?displayProperty=nameWithType>.  

## <a name="thread-pool-characteristics"></a>Характеристики пула потоков

Потоки из пула являются [фоновыми](foreground-and-background-threads.md). Для каждого потока используется размер стека по умолчанию, поток запускается с приоритетом по умолчанию и находится в многопотоковом подразделении. Когда поток в пуле завершает свою задачу, он возвращается в очередь потоков в состоянии ожидания. С этого момента его можно использовать вновь. Повторное использование позволяет приложениям избежать дополнительных затрат на создание новых потоков для каждой задачи.
  
Для каждого процесса существует только один пул потоков.  
  
### <a name="exceptions-in-thread-pool-threads"></a>Исключения в потоках из пула потоков

Необработанные исключения в потоках из пула приводят к завершению процесса. Есть три исключения из этого правила:  
  
- Исключение <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> возникает в потоке пула вследствие вызова <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.  
- Исключение <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> возникает в потоке пула вследствие выгрузки домена приложения.  
- Среда CLR или процесс ведущего приложения прерывает выполнение потока.  
  
См. дополнительные сведения об [исключениях в управляемых потоках](exceptions-in-managed-threads.md).  
  
### <a name="maximum-number-of-thread-pool-threads"></a>Максимальное число потоков в пуле потоков

Число операций, которое можно поставить в очередь в пуле потоков, ограничено только доступной памятью. Однако пул потоков имеет ограничение на число потоков, которое можно активировать в процессе одновременно. Если все потоки в пуле заняты, дополнительные рабочие элементы помещаются в очередь и ожидают их освобождения. Начиная с .NET Framework 4, размер пула потоков по умолчанию для какого-либо процесса зависит от нескольких факторов, таких как размер виртуального адресного пространства. Процесс может вызвать метод <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> для определения количества потоков.  
  
Вы можете управлять максимальным количеством потоков с помощью методов <xref:System.Threading.ThreadPool.GetMaxThreads%2A?displayProperty=nameWithType> и <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.  

> [!NOTE]
> В коде, содержащем среду CLR, этот размер можно задать с помощью метода [`ICorThreadpool::CorSetMaxThreads`](../../framework/unmanaged-api/hosting/icorthreadpool-corsetmaxthreads-method.md).  
  
### <a name="thread-pool-minimums"></a>Минимальные значения пула потоков

Пул потоков предоставляет новые рабочие потоки или потоки завершения ввода-вывода по запросу, пока не будет достигнут заданный минимум для каждой категории. Для получения этих минимальных значений можно использовать метод <xref:System.Threading.ThreadPool.GetMinThreads%2A?displayProperty=nameWithType>.  
  
> [!NOTE]
> Если потребность низкая, фактическое количество потоков из пула потоков может быть ниже минимальных значений.  
  
При достижении минимума пул потоков может создавать дополнительные потоки или ожидать завершения некоторых задач. Начиная с .NET Framework 4, пул потоков создает и уничтожает рабочие потоки в целях оптимизации пропускной способности, которая определяется как количество задач, выполняемых в единицу времени. Слишком малое количество потоков может препятствовать оптимальному использованию доступных ресурсов, тогда как слишком большое их количество может усиливать конкуренцию за ресурсы.  
  
> [!CAUTION]
> Для увеличения минимального количества бездействующих потоков можно использовать метод <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>. Однако необоснованное увеличение этих значений может привести к снижению производительности. Если одновременно запускается слишком много задач, все они могут выполняться слишком медленно. В большинстве случаев пул потоков работает наилучшим образом, если он использует собственный алгоритм выделения потоков.  

## <a name="using-the-thread-pool"></a>Использование пула потоков

Начиная с .NET Framework 4, самым простым способом использования пула потоков является применение [библиотеки параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md). По умолчанию такие типы TPL, как <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>, используют потоки из пула для выполнения задач.

Пул потоков также можно использовать путем вызова <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> из управляемого кода (или [`ICorThreadpool::CorQueueUserWorkItem`](../../framework/unmanaged-api/hosting/icorthreadpool-corqueueuserworkitem-method.md) из неуправляемого кода) и передачи делегата <xref:System.Threading.WaitCallback?displayProperty=nameWithType>, представляющего метод, который выполняет задачу.

Другим способом использования пула потоков является помещение в очередь рабочих элементов, которые имеют отношение к операции ожидания, с помощью метода <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> и передача дескриптора <xref:System.Threading.WaitHandle?displayProperty=nameWithType>, который вызывает метод, представленный делегатом <xref:System.Threading.WaitOrTimerCallback?displayProperty=nameWithType>, при получении сигнала или истечении времени ожидания. Потоки из пула потоков используются для вызова методов обратного вызова.  

Примеры см. по ссылкам на страницы API.
  
## <a name="skipping-security-checks"></a>Пропуск проверок безопасности

Пул потоков также предоставляет методы <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> и <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType>. Используйте эти методы только в том случае, если вы уверены, что стек вызывающего объекта не важен для проверок безопасности, осуществляемых во время выполнения задачи в очереди. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> и <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> перехватывают стек вызывающего объекта, который объединяется со стеком потока из пула потоков, когда поток начинает выполнять задачу. Если требуется проверка безопасности, проверяется весь стек. Несмотря на обеспечение безопасности, такая проверка также влияет на производительность.  

## <a name="when-not-to-use-thread-pool-threads"></a>Когда не следует использовать потоки из пула потоков

Существует ряд сценариев, в которых следует создавать собственные потоки и работать с ними, а не использовать потоки из пула:  
  
- Необходим основной поток.  
- Поток должен иметь определенный приоритет.  
- Имеются задачи, которые приводят к блокировке потока на длительное время. Для пула потоков определено максимальное количество потоков, поэтому большое число заблокированных потоков в пуле может препятствовать запуску задач.  
- Необходимо поместить потоки в однопотоковое подразделение. Все потоки <xref:System.Threading.ThreadPool> находятся в многопотоковом подразделении.  
- Необходимо иметь постоянное удостоверение, сопоставленное с потоком, или назначить поток задаче.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>
- [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md)
- [Практическое руководство. Возвращение значения из задачи](../parallel-programming/how-to-return-a-value-from-a-task.md)
- [Объекты и функциональные возможности работы с потоками](threading-objects-and-features.md)
- [Потоки и работа с потоками](threads-and-threading.md)
- [Asynchronous File I/O](../io/asynchronous-file-i-o.md)
- [Таймеры](timers.md)
