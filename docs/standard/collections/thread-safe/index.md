---
title: "Потокобезопасные коллекции | Microsoft Docs"
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
  - "потокобезопасные коллекции, обзор"
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
caps.latest.revision: 24
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 24
---
# Потокобезопасные коллекции
В платформе [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] доступно пространство имен <xref:System.Collections.Concurrent?displayProperty=fullName>, которое содержит несколько классов коллекций, которые являются потокобезопасными и масштабируемыми.  Несколько потоков могут безопасно и эффективно добавлять и удалять элементы из таких коллекций, не требуя при этом дополнительной синхронизации в пользовательском коде.  При написании нового кода следует использовать классы параллельных коллекций каждый раз, когда коллекция будет записывать одновременно для нескольких потоков.  Если выполняется только чтение из общей коллекции, можно использовать классы в пространстве имен <xref:System.Collections.Generic?displayProperty=fullName>.  Не рекомендуется использовать классы коллекций версии 1.0, если в качестве целевой среды выполнения не требуется платформа .NET Framework версии 1.1 или предыдущие версии.  
  
## Синхронизация потоков в пространстве имен Collections на платформах .NET Framework версий 1.0 и 2.0  
 Доступные на платформе .NET Framework 1.0 коллекции находятся в пространстве имен <xref:System.Collections?displayProperty=fullName>.  Эти коллекции, которые содержат часто используемые класс <xref:System.Collections.ArrayList> и класс <xref:System.Collections.Hashtable>, предоставляют некоторую потокобезопасность посредством свойства `Synchronized`, которое возвращает потокобезопасную программу\-оболочку вокруг коллекции.  Работа программы оболочки заключается в блокировке всей коллекции при каждой операции добавления или удаления.  Поэтому каждый поток, который пытается получить доступ к коллекции, должен ждать своей очереди для получения блокировки.  Такой подход не является масштабируемым и может привести к значительному снижению производительности для больших коллекций.  Также такой подход не защищен полностью от состояния гонки.  Дополнительные сведения см. в разделе [Синхронизация в универсальных коллекциях](http://go.microsoft.com/fwlink/?LinkID=161130) на веб\-сайте MSDN.  
  
 Доступные на платформе .NET Framework 2.0 классы коллекций находятся в пространстве имен <xref:System.Collections.Generic?displayProperty=fullName>.  Они включают классы <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> и так далее.  Эти классы предоставляют улучшенную безопасность типа и производительность по сравнению с классами на платформе .NET Framework 1.0.  Однако классы коллекций платформы .NET Framework 2.0 не обеспечивают синхронизацию потоков. Пользовательский код должен обеспечивать всю синхронизацию при параллельном добавлении элементов в несколько потоков или удалении элементов из них.  
  
 Рекомендуются классы параллельных коллекций на платформе [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] так как они предоставляют не только безопасность типа классов коллекций платформы .NET Framework 2.0, но и большую эффективность, более полную потокобезопасность по сравнению с коллекциями [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)].  
  
## Механизм блокировки мелких фрагментов данных и механизм, свободный от блокировки  
 Отдельные из типов параллельных коллекций используют механизмы упрощенной синхронизации, например, <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim>, <xref:System.Threading.CountdownEvent>, которые появились на платформе [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  Эти типы синхронизации обычно используют *цикличную работу* для коротких промежутков перед помещением потока в фактическое состояние ожидания.  При условии, что время ожидания предполагается очень коротким, цикличность требует значительно меньших затрат компьютерных ресурсов, чем ожидание, которое включает в себя переход в режим ядра, который требует больших затрат компьютерных ресурсов.  Для классов коллекций, которые используют цикличность, эта эффективность означает, что множество потоков могут добавлять и удалять большое количество элементов.  Дополнительные сведения о цикличных блокировках см. в разделе [SpinLock](../../../../docs/standard/threading/spinlock.md) и [SpinWait](../../../../docs/standard/threading/spinwait.md).  
  
 Классы <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601> вообще не используют блокировки.  Вместо этого для достижения потокобезопасности они используют операции <xref:System.Threading.Interlocked>.  
  
> [!NOTE]
>  Так как классы параллельных коллекций поддерживают интерфейс <xref:System.Collections.ICollection>, они предоставляют реализации для свойства <xref:System.Collections.ICollection.IsSynchronized%2A> и свойства <xref:System.Collections.ICollection.SyncRoot%2A> даже если эти свойства не имеют значения.  Свойство `IsSynchronized` всегда возвращает значение `false`, а свойство `SyncRoot` всегда имеет значение `null` \(`Nothing` в Visual Basic\).  
  
 В следующей таблице перечислены типы коллекций в пространстве имен <xref:System.Collections.Concurrent?displayProperty=fullName>.  
  
|Тип|Описание|  
|---------|--------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|Предоставляет возможности блокировки и ограничения для всех типов, которые реализуют интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.  Для получения дополнительной информации см. [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|Потокобезопасная реализация словаря пар "ключ\-значение".|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|Потокобезопасная реализация очереди с типом "первым поступил — первым обслужен" \(FIFO\).|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|Потокобезопасная реализация стека с типом "последним поступил — первым обслужен" \(LIFO\).|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|Потокобезопасная реализация неупорядоченной коллекции элементов.|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|Это интерфейс, тип которого должен быть реализован для использования в классе `BlockingCollection`.|  
  
## Связанные разделы  
  
|Название|Описание|  
|--------------|--------------|  
|[Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|Приводится описание функциональных возможностей, которые предоставляются типом <xref:System.Collections.Concurrent.BlockingCollection%601>.|  
|[Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|Приводится описание порядка добавления и удаления элементов из класса <xref:System.Collections.Concurrent.ConcurrentDictionary%602>|  
|[Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|Приводится описание порядка добавления и получения элементов из заблокированной коллекции без использования перечислителя, доступного только для чтения.|  
|[Практическое руководство. Добавление функций границы и блокировки в коллекцию](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|Приводится описание порядка использования всех классов коллекций в качестве базового механизма хранения для коллекции <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.|  
|[Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|Приводится описание порядка использования конструкции `foreach`, \(`For Each` в Visual Basic\) для удаления всех элементов в заблокированной коллекции.|  
|[Практическое руководство. Использование массивов для блокировки коллекций в конвейере](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|Приводится описание порядка одновременного использования нескольких заблокированных коллекций для реализации конвейера.|  
|[Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|Показано, как использовать параллельный контейнер для повышения производительности в сценариях, где можно переиспользовать объекты вместо постоянного создания новых.|  
  
## Справочные сведения  
 <xref:System.Collections.Concurrent?displayProperty=fullName>