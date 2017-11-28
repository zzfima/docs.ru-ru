---
title: "Потокобезопасные коллекции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: thread-safe collections, overview
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
caps.latest.revision: "24"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b5394cd2e9c9fa2b0cacb93ddf2cf05b33fabc71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="thread-safe-collections"></a>Потокобезопасные коллекции
В [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] введено пространство имен <xref:System.Collections.Concurrent?displayProperty=nameWithType>, включающее несколько потокобезопасных и масштабируемых классов коллекций. Несколько потоков могут безопасно и эффективно добавлять и удалять элементы из таких коллекций, не требуя при этом дополнительной синхронизации в пользовательском коде. При написании нового кода следует использовать классы параллельных коллекций каждый раз, когда коллекция будет записывать одновременно для нескольких потоков. Если выполняется только чтение из общей коллекции, вы можете использовать классы в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType>. Мы рекомендуем использовать классы коллекций версии 1.0 только в том случае, если вам нужна среда выполнения .NET Framework до версии 1.1 включительно.  
  
## <a name="thread-synchronization-in-the-net-framework-10-and-20-collections"></a>Синхронизация потоков в коллекциях .NET Framework версий 1.0 и 2.0  
 Коллекции, представленные в .NET Framework 1.0, находятся в пространстве имен <xref:System.Collections?displayProperty=nameWithType>. Эти коллекции, которые содержат часто используемые классы <xref:System.Collections.ArrayList> и <xref:System.Collections.Hashtable>, обеспечивают определенную степень потокобезопасности посредством свойства `Synchronized`, которое создает для коллекции потокобезопасную программу-оболочку. Работа программы оболочки заключается в блокировке всей коллекции при каждой операции добавления или удаления. Поэтому каждый поток, который пытается получить доступ к коллекции, должен ждать своей очереди для получения блокировки. Такой подход не является масштабируемым и может привести к значительному снижению производительности для больших коллекций. Также такой подход не защищен полностью от состояния гонки. Дополнительные сведения см. на веб-сайте MSDN в [блоге о синхронизации в универсальных коллекциях](http://go.microsoft.com/fwlink/?LinkID=161130).  
  
 Классы коллекций, представленные в .NET Framework 2.0, находятся в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType>. К ним относятся <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> и др. Эти классы отличаются улучшенной безопасностью типа и производительностью по сравнению с классами .NET Framework 1.0. Однако классы коллекций .NET Framework 2.0 не обеспечивают синхронизацию потоков. Пользовательский код должен обеспечивать всю синхронизацию при параллельном добавлении элементов в несколько потоков или удалении элементов из них.  
  
 Мы рекомендуем использовать классы параллельных коллекций [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], так как они предоставляют не только безопасность типа классов NET Framework 2.0, но и большую эффективность, более полную потокобезопасность по сравнению с коллекциями [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)].  
  
## <a name="fine-grained-locking-and-lock-free-mechanisms"></a>Механизм блокировки мелких фрагментов данных и механизм, свободный от блокировки  
 Некоторые типы многопоточных коллекций используют упрощенные механизмы синхронизации, например <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim> и <xref:System.Threading.CountdownEvent>, которые впервые введены в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]. Эти типы синхронизации обычно используют *цикличную работу* для коротких промежутков перед помещением потока в фактическое состояние ожидания. При условии, что время ожидания предполагается очень коротким, цикличность требует значительно меньших затрат компьютерных ресурсов, чем ожидание, которое включает в себя переход в режим ядра, требующий больших затрат компьютерных ресурсов. Для классов коллекций, которые используют цикличность, эта эффективность означает, что множество потоков могут добавлять и удалять большое количество элементов. Дополнительные сведения о цикличности и блокировках см. в статья [SpinLock](../../../../docs/standard/threading/spinlock.md) и [SpinWait](../../../../docs/standard/threading/spinwait.md).  
  
 Классы <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601> не используют блокировку. Вместо этого они используют операции класса <xref:System.Threading.Interlocked> для обеспечения потокобезопасности.  
  
> [!NOTE]
>  Так как классы многопоточных коллекций поддерживают интерфейс <xref:System.Collections.ICollection>, они включают реализации для свойств <xref:System.Collections.ICollection.IsSynchronized%2A> и <xref:System.Collections.ICollection.SyncRoot%2A>, даже хотя эти свойства никак не используются. `IsSynchronized` всегда возвращает `false`, а `SyncRoot` всегда имеет значение `null` (`Nothing` в Visual Basic).  
  
 В следующей таблице перечислены типы коллекций в пространстве имен <xref:System.Collections.Concurrent?displayProperty=nameWithType>.  
  
|Тип|Описание|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|Предоставляет возможности блокировки и ограничения для всех типов, реализующих интерфейс <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>. Дополнительные сведения см. в разделе [Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|Потокобезопасная реализация словаря пар "ключ-значение".|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|Потокобезопасная реализация очереди с типом "первым поступил — первым обслужен" (FIFO).|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|Потокобезопасная реализация стека с типом "последним поступил — первым обслужен" (LIFO).|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|Потокобезопасная реализация неупорядоченной коллекции элементов.|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|Это интерфейс, тип которого должен быть реализован для использования в классе `BlockingCollection`.|  
  
## <a name="related-topics"></a>Связанные разделы  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Общие сведения о коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|Приводится описание функциональных возможностей, которые предоставляются типом <xref:System.Collections.Concurrent.BlockingCollection%601>.|  
|[Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|Приводится описание добавления и удаления элементов в классе <xref:System.Collections.Concurrent.ConcurrentDictionary%602>|  
|[Практическое руководство. Добавление и удаление отдельных элементов коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|Приводится описание порядка добавления и получения элементов из заблокированной коллекции без использования перечислителя, доступного только для чтения.|  
|[Практическое руководство. Добавление функций границы и блокировки в коллекцию](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|Приводится описание порядка использования всех классов коллекций в качестве базового механизма хранения для коллекции <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>.|  
|[Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|Описание порядка использования `foreach` (`For Each` в Visual Basic) для удаления всех элементов в заблокированной коллекции.|  
|[Практическое руководство. Использование массивов для блокировки коллекций в конвейере](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|Приводится описание порядка одновременного использования нескольких заблокированных коллекций для реализации конвейера.|  
|[Практическое руководство. Создание пула объектов с помощью класса ConcurrentBag](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|Показано, как применить параллельный контейнер для повышения производительности в сценариях, где можно повторно использовать объекты вместо постоянного создания новых.|  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>
