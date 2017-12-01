---
title: "Структуры данных для параллельного программирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>Структуры данных для параллельного программирования
.NET Framework версии 4 представлено несколько новых типов, которые полезны в параллельном программировании, включая набор классов параллельных коллекций, примитивы упрощенной синхронизации и типы отложенной инициализации. Эти типы можно использовать с любым кодом многопоточного приложения, включая библиотеку параллельных задач и PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Классы параллельных коллекций  
 Классы коллекций в <xref:System.Collections.Concurrent?displayProperty=nameWithType> пространства имен предоставляют поточно-Добавление и удаление операций, которые избежать блокировок, по возможности и использовать детально настроенные блокировку, где необходимы блокировки. В отличие от коллекций, которые впервые появились в .NET Framework версий 1.0 и 2.0 класс параллельных коллекций не требуется пользовательский код, чтобы занять все блокировки при доступе к элементам. Классы параллельных коллекций может значительно повысить производительность по типам например <xref:System.Collections.ArrayList?displayProperty=nameWithType> и <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (с реализованной пользователем блокировкой) в сценариях, где несколько потоков добавляют и удаляют элементы из коллекции.  
  
 В следующей таблице перечислены новые классы параллельных коллекций:  
  
|Тип|Описание|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Предоставляет возможности блокировки и ограничения для потокобезопасных коллекций, реализующих <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Производитель потоки блокируются, если нет доступных слотов или если коллекция является полной. Потоки-потребители блокируются, если коллекция пуста. Этот тип также поддерживает неблокирующий доступ потребителей и производителей. <xref:System.Collections.Concurrent.BlockingCollection%601>можно использовать в качестве базового класса или резервного хранилища для предоставления блокировки и ограничения для любого класса коллекции, который поддерживает <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Потокобезопасной реализацию, которая предоставляет масштабируемые операции добавления и получения.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Тип параллельного и масштабируемого словаря.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Параллельная и масштабируемая очередь FIFO.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Параллельный и масштабируемый стек LIFO.|  
  
 Дополнительные сведения см. в разделе [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Примитивы синхронизации  
 Новые примитивы синхронизации в <xref:System.Threading?displayProperty=nameWithType> пространства имен обеспечивают детализацию параллелизма и повышенную производительность благодаря исключению ресурсоемких механизмов блокировки, которые используются в устаревшем многопоточном коде. Некоторые из новых типов, таких как <xref:System.Threading.Barrier?displayProperty=nameWithType> и <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> имеют нет аналогов в более ранних версиях платформы .NET Framework.  
  
 В следующей таблице перечислены новые типы синхронизации:  
  
|Тип|Описание|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Позволяет нескольким потокам работать параллельно с алгоритмом, предоставляя точку, с которой каждая задача указывают поступления и затем блокироваться, пока не поступили некоторые или все задачи. Дополнительные сведения см. в разделе [Барьер](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Упрощает сценарии разветвления и объединения, предоставляя механизм легко встречи. Дополнительные сведения см. в разделе [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Примитив синхронизации, аналогично <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim>облегченный, но может использоваться только для обмена данными внутри процесса. Дополнительные сведения см. в разделе [ManualResetEvent и ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Примитив синхронизации, который ограничивает количество потоков, которые могут параллельно обращаться к ресурсу или пулу ресурсов. Дополнительные сведения см. в разделе [Semaphore и SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Примитив взаимно исключающей блокировки, что вызывающий поток, который пытается получить блокировку для ожидания в цикле или *счетчик*, в течение заданного времени до возврата такта. В сценариях, где дожидался блокировки должен быть коротким <xref:System.Threading.SpinLock> предлагает более высокую производительность по сравнению с другими формами блокировки. Дополнительные сведения см. в разделе [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Небольшой, простое тип, который будет вращаться в указанное время и в итоге переходу потока в состояние ожидания при превышении прокруток.  Дополнительные сведения см. в разделе [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Дополнительные сведения:  
  
-   [Практическое руководство. SpinLock и низкоуровневая синхронизация](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [Как: синхронизация параллельных операций с барьером](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Классы отложенная инициализация  
 С отложенной инициализацией не выделить память для объекта, если она нужна. Отложенная инициализация может повысить производительность, равномерно распределения объекты во времени существования программы. Можно включить отложенную инициализацию любого пользовательского типа, упаковка типа <xref:System.Lazy%601>.  
  
 В следующей таблице перечислены типы отложенной инициализации.  
  
|Тип|Описание|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Предоставляет упрощенный, поточно ориентированного отложенной инициализации.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Предоставляет неактивно инициализированное значение на основе каждого потока, при этом каждый поток неактивно вызывает функцию инициализации.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Предоставляет статические методы, которые избежать необходимости выделения выделенный экземпляр отложенной инициализации. Вместо них используется ссылки, чтобы убедиться, что целевые объекты были инициализированы, поскольку они доступны.|  
  
 Дополнительные сведения см. в статье [Отложенная инициализация](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Агрегатные исключения  
 <xref:System.AggregateException?displayProperty=nameWithType> Типа можно использовать для фиксации нескольких исключений, создаваемых в отдельных потоках одновременно и возвращают их в присоединяемый поток в виде одного исключения. <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> И <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> использовать типы и PLINQ <xref:System.AggregateException> широко для этой цели. Дополнительные сведения см. в разделе [NIB: Практическое: обработки исключений, создаваемых задачами](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d) и [как: обработка исключений в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
