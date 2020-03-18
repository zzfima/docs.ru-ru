---
title: Структуры данных для параллельного программирования
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
ms.openlocfilehash: a2271feae78100940b4ecac3c42c9bfefa7e1769
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73123151"
---
# <a name="data-structures-for-parallel-programming"></a>Структуры данных для параллельного программирования
На платформе .NET Framework версии 4 появились несколько новых типов для параллельного программирования, включая набор классов параллельных коллекций, упрощенные примитивы синхронизации и типы отложенной инициализации. Эти типы можно использовать с любым кодом многопоточного приложения, включая библиотеку параллельных задач и PLINQ.  
  
## <a name="concurrent-collection-classes"></a>Классы параллельных коллекций  
 Классы коллекций в пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> поддерживают потокобезопасные операции добавления и удаления, которые избегают блокировок везде, где это возможно, и применяют только детально настроенные блокировки. В отличие от коллекций, которые появились в .NET Framework версий 1.0 и 2.0, класс параллельных коллекций не требует использовать блокировки в пользовательском коде для доступа к элементам. Классы параллельных коллекций могут значительно повысить производительность по сравнению с типами <xref:System.Collections.ArrayList?displayProperty=nameWithType> и <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (где блокировка реализуется пользователем) в сценариях одновременного добавления и удаления элементов коллекции из нескольких потоков.  
  
 В следующей таблице перечислены новые классы параллельных коллекций.  
  
|Type|Описание:|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|Предоставляет возможности блокировки и ограничения для потокобезопасных коллекций, реализующих <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>. Потоки-производителя блокируются, если нет доступных слотов или коллекция заполнена. Потоки-потребители блокируются, если коллекция пуста. Этот тип также поддерживает неблокирующий доступ для потребителей и производителей. <xref:System.Collections.Concurrent.BlockingCollection%601> можно использовать в качестве базового класса или резервного хранилища с поддержкой блокировок и ограничений для любого класса коллекции с поддержкой <xref:System.Collections.Generic.IEnumerable%601>.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|Потокобезопасная реализация контейнера, которая предоставляет масштабируемые операции добавления и получения.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|Тип параллельного и масштабируемого словаря.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|Параллельная и масштабируемая очередь FIFO.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|Параллельный и масштабируемый стек LIFO.|  
  
 Дополнительные сведения см. в разделе [Потокобезопасные коллекции](../../../docs/standard/collections/thread-safe/index.md).  
  
## <a name="synchronization-primitives"></a>Примитивы синхронизации  
 Новые примитивы синхронизации в пространстве имен <xref:System.Threading?displayProperty=nameWithType> обеспечивают детально настраиваемый параллелизм и более высокую производительность за счет устранения ресурсоемких механизмов блокировки из старого кода для многопоточной работы. Некоторые из новых типов, например <xref:System.Threading.Barrier?displayProperty=nameWithType> и <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>, не имели аналогов в более ранних версиях платформы .NET Framework.  
  
 В следующей таблице перечислены новые типы синхронизации.  
  
|Type|Описание:|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|Позволяет нескольким потокам работать над выполнением алгоритма параллельно, поддерживая точку регистрации, в которой каждая задача отмечает свою доступность и ожидает новых задач. Дополнительные сведения см. в разделе [Барьер](../../../docs/standard/threading/barrier.md).|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|Упрощает сценарии ветвления и соединения, предоставляя удобный механизм взаимодействия. Более подробную информацию можно найти в [описании события CountdownEvent](../../../docs/standard/threading/countdownevent.md).|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|Примитив синхронизации, аналогичный <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>. <xref:System.Threading.ManualResetEventSlim> менее требователен к ресурсам, но пригоден только для обмена данными внутри процесса.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|Примитив синхронизации, который ограничивает количество потоков, одновременно обращающихся к ресурсу или пулу ресурсов. Дополнительные сведения см. в [описании классов Semaphore и SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|Примитив взаимоисключающей блокировки, при использовании которого поток, который пытается получить блокировку, применяет *цикл ожидания* в течение заданного времени, прежде чем получить свою часть времени. В сценариях, где прогнозируется короткий период ожидания блокировки, <xref:System.Threading.SpinLock> обеспечит более высокую производительность по сравнению с другими формами блокировки. Дополнительные сведения см. в [описании SpinLock](../../../docs/standard/threading/spinlock.md).|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|Небольшой и нетребовательный к ресурсам тип, который реализует небольшую паузу, и только по истечении заданного времени переходит в состояние ожидания.  Дополнительные сведения см. в [описании SpinWait](../../../docs/standard/threading/spinwait.md).|  
  
 Дополнительные сведения можно найти в разделе  
  
- [Практическое руководство. SpinLock и низкоуровневая синхронизация](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
- [Практическое руководство. Синхронизация параллельных операций с барьером](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## <a name="lazy-initialization-classes"></a>Классы отложенной инициализации  
 При использовании отложенной инициализации память выделяется объекту только в тот момент, когда она нужна. Отложенная инициализация позволяет повысить производительность, равномерно распределяя процессы выделения объектов на вест период существования программы. Чтобы включить отложенную инициализацию для любого пользовательского типа, упакуйте в него тип <xref:System.Lazy%601>.  
  
 В следующей таблице перечислены типы отложенной инициализации.  
  
|Type|Описание:|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|Легкая и потокобезопасная реализация отложенной инициализации.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|Предоставляет отложенно инициализированное значение для каждого потока, при этом каждый поток вызывает функцию отложенной инициализации.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|Предоставляет статические методы, которые избавляют от необходимости выделять экземпляр отложенной инициализации. Вместо этого он использует ссылки, гарантирующие инициализацию целевых объектов при первом обращении к ним.|  
  
 Дополнительные сведения см. в статье [Отложенная инициализация](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="aggregate-exceptions"></a>Агрегатные исключения  
 Тип <xref:System.AggregateException?displayProperty=nameWithType> позволяет захватить несколько исключений, создаваемых одновременно в нескольких отдельных потоках, и передать их в присоединяемый поток в виде одного исключения. Типы <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, а также PLINQ, широко используют для этой цели <xref:System.AggregateException>. Дополнительные сведения см. в статьях [Обработка исключений](../../../docs/standard/parallel-programming/exception-handling-task-parallel-library.md) и [Практическое руководство. Обработка исключений в запросах PLINQ](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- <xref:System.Threading?displayProperty=nameWithType>
- [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)
