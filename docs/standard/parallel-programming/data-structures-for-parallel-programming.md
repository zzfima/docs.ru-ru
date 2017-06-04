---
title: "Data Structures for Parallel Programming | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "data structures, multi-threading"
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Data Structures for Parallel Programming
В .NET Framework версии 4 представлено несколько новых типов, полезных в параллельном программировании, включая набор классов параллельных коллекций, примитивы упрощенной синхронизации и типы неактивной инициализации.  Эти типы можно использовать с любым кодом многопоточного приложения, включая библиотеку параллельных задач и PLINQ.  
  
## Классы параллельных коллекций  
 Классы коллекций в пространстве имен <xref:System.Collections.Concurrent?displayProperty=fullName> предоставляют потокобезопасные операции добавления и удаления, которые по возможности избегают блокировок и используют блокировку мелких фрагментов данных там, где необходима блокировка.  В отличие от коллекций, которые были введены в .NET Framework версий 1.0 и 2.0, класс параллельных коллекций не требует, чтобы пользовательский код принимал какие\-либо блокировки при доступе к элементам.  Классы параллельных коллекций могут значительно увеличить производительность по сравнению с типами, такими как <xref:System.Collections.ArrayList?displayProperty=fullName> и <xref:System.Collections.Generic.List%601?displayProperty=fullName> \(с реализованной пользователем блокировкой\), в сценариях, где несколько потоков добавляют и удаляют элементы из коллекции.  
  
 В следующей таблице перечислены новые классы параллельных коллекций.  
  
|Тип|Описание|  
|---------|--------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>|Предоставляет возможности блокировки и ограничения для потокобезопасных коллекций, реализующих <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName>.  Потоки\-производители блокируются, если слоты отсутствуют или коллекция является полной.  Потоки\-потребители блокируются, если коллекция пуста.  Этот тип также поддерживает неблокирующий доступ потребителей и производителей.  Коллекцию <xref:System.Collections.Concurrent.BlockingCollection%601> можно использовать в качестве базового класса или резервного хранилища для предоставления блокировки и ограничения для любого класса коллекции, поддерживающего <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>|Потокобезопасная реализация наборов, предоставляющая масштабируемые операции добавления и получения.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>|Тип параллельного и масштабируемого словаря.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>|Параллельная и масштабируемая очередь FIFO.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>|Параллельный и масштабируемый стек LIFO.|  
  
 Для получения дополнительной информации см. [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
## Примитивы синхронизации  
 Новые примитивы синхронизации в пространстве имен <xref:System.Threading?displayProperty=fullName> обеспечивают детализацию параллелизма и повышенную производительность благодаря исключению ресурсоемких механизмов блокировки, которые используются в устаревшем многопоточном коде.  Некоторые новые типы, например <xref:System.Threading.Barrier?displayProperty=fullName> и <xref:System.Threading.CountdownEvent?displayProperty=fullName>, не имеют аналогов в более ранних выпусках платформы .NET Framework.  
  
 В следующей таблице перечислены новые типы синхронизации.  
  
|Тип|Описание|  
|---------|--------------|  
|<xref:System.Threading.Barrier?displayProperty=fullName>|Включает несколько потоков для параллельной работы с алгоритмом, предоставляя точку, в которой каждая задача может сигнализировать о своем поступлении, а затем блокироваться до тех пор, пока не поступят некоторые или все задачи.  Для получения дополнительной информации см. [Barrier](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=fullName>|Упрощает сценарии разветвления и объединения, предоставляя простой механизм сближения.  Для получения дополнительной информации см. [CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>|Примитив синхронизации, аналогичный <xref:System.Threading.ManualResetEvent?displayProperty=fullName>.  <xref:System.Threading.ManualResetEventSlim> является более простым типом, но может быть использован для взаимодействия внутри процесса.  Для получения дополнительной информации см. [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md).|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=fullName>|Примитив синхронизации, ограничивающий количество потоков, которые могут параллельно обращаться к ресурсу или пулу ресурсов.  Для получения дополнительной информации см. [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=fullName>|Примитив взаимно исключающей блокировки, вызывающий поток, который пытается получить блокировку для ожидания в цикле или *spin* для периода времени до возврата такта.  В сценариях, в которых предполагается, что ожидание блокировки будет коротким, <xref:System.Threading.SpinLock> предлагает более высокую производительность по сравнению с другими формами блокировки.  Для получения дополнительной информации см. [SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=fullName>|Небольшой более простой тип, который будет вращаться в течение определенного времени и со временем приведет к переходу потока в состояние ожидания, если будет превышено число прокруток.  Для получения дополнительной информации см. [SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## Классы неактивной инициализации  
 При неактивной инициализации память для объекта не выделяется, пока не понадобится.  Неактивная инициализация может повысить производительность, равномерно распределения объекты во времени существования программы.  Неактивную инициализацию любого пользовательского типа можно реализовать, создав программу\-оболочку для типа <xref:System.Lazy%601>.  
  
 В следующей таблице перечислены типы неактивной инициализации.  
  
|Тип|Описание|  
|---------|--------------|  
|<xref:System.Lazy%601?displayProperty=fullName>|Предоставляет упрощенную, потокобезопасную неактивную инициализацию.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=fullName>|Предоставляет неактивно инициализированное значение на основе отдельного потока, при этом каждый поток неактивно вызывает функцию инициализации.|  
|<xref:System.Threading.LazyInitializer?displayProperty=fullName>|Предоставляет статические методы, устраняющие потребность в выделенном экземпляре неактивной инициализации.  Вместо этого используются ссылки для обеспечения инициализации целевых объектов при доступе к ним.|  
  
 Для получения дополнительной информации см. [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Агрегатные исключения  
 Тип <xref:System.AggregateException?displayProperty=fullName> можно использовать для фиксации нескольких исключений, параллельно создаваемых в отдельных потоках, и возвращения их в присоединяемый поток в виде одного исключения.  Типы <xref:System.Threading.Tasks.Task?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel?displayProperty=fullName>, а также PLINQ активно используют для этого исключение <xref:System.AggregateException>.  Дополнительные сведения см. в разделах [NIB: How to: Handle Exceptions Thrown by Tasks](http://msdn.microsoft.com/ru-ru/d6c47ec8-9de9-4880-beb3-ff19ae51565d) и [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 <xref:System.Threading?displayProperty=fullName>   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)