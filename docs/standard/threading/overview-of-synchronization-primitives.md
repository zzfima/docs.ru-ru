---
title: "Overview of Synchronization Primitives | Microsoft Docs"
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
  - "synchronization, threads"
  - "threading [.NET Framework],synchronizing threads"
  - "managed threading"
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Overview of Synchronization Primitives
Платформа .NET Framework предоставляет ряд примитивов синхронизации для управления взаимодействием потоков и предотвращения состояний гонки.  Их можно условно разделить на три категории: блокировка, сигнал и блокированные операции.  
  
 Эти категории точно не определены: некоторые механизмы синхронизации имеют признаки нескольких категорий; события, которые освобождают по одному потоку за раз, функционируют как блокировки; снятие любой блокировки может быть воспринято как сигнал, а блокированные операции могут быть использованы для создания блокировок.  Однако эти категории все же полезны.  
  
 Важно помнить, что синхронизация потоков выполняется совместно.  Если хотя бы один поток обходит механизм синхронизации и получает доступ напрямую к защищенному ресурсу, такой механизм синхронизации не может считаться эффективным.  
  
 Обзор включает следующие разделы.  
  
-   [Блокировка](#locking)  
  
-   [Сигнальный NaN](#signaling)  
  
-   [Типы упрощенной синхронизации](#lightweight_synchronization_types)  
  
-   [SpinWait](#spinwait)  
  
-   [Блокируемые операции](#interlocked_operations)  
  
<a name="locking"></a>   
## Блокировка  
 Блокировки предоставляют единовременное управление ресурсом одному потоку или определенному количеству потоков.  Поток, запрашивающий монопольную блокировку, если блокировка уже используется, блокируется до того момента, как блокировка станет доступной.  
  
### Монопольные блокировки  
 Самым простым способом блокировки является оператор `lock` в C\# \(`SyncLock` в Visual Basic\), который управляет доступом к блоку кода.  Как правило, этот блок называется критической секцией.  Оператор `lock` реализуется с помощью методов <xref:System.Threading.Monitor.Enter%2A> и <xref:System.Threading.Monitor.Exit%2A> класса <xref:System.Threading.Monitor>. Он использует блок `try…catch…finally` для обеспечения снятия блокировки.  
  
 В целом, использование оператора `lock` для защиты небольших блоков кода, никогда не распространяющееся на несколько методов, является лучшим способом использования класса <xref:System.Threading.Monitor>.  Несмотря на все свои возможности, класс <xref:System.Threading.Monitor> подвержен потере блокировок и взаимоблокировок.  
  
#### Класс Monitor  
 Класс <xref:System.Threading.Monitor> предоставляет дополнительные возможности, которые можно использовать вместе с оператором `lock`.  
  
-   Метод <xref:System.Threading.Monitor.TryEnter%2A> позволяет через указанное время разблокировать поток, который заблокирован в ожидании предоставления ресурса.  Он возвращает логическое значение, указывающее на успешность выполнения или сбой, которое можно использовать для выявления и устранения возможных взаимоблокировок.  
  
-   Метод <xref:System.Threading.Monitor.Wait%2A> вызывается потоком в критической секции.  Он отдает управление ресурсом и блокирует поток до тех пор, пока ресурс снова станет доступным.  
  
-   Методы <xref:System.Threading.Monitor.Pulse%2A> и <xref:System.Threading.Monitor.PulseAll%2A> разрешают потоку, который должен снять блокировку или вызвать метод <xref:System.Threading.Monitor.Wait%2A>, поместить один или несколько потоков в очередь готовности, чтобы они могли получить блокировку.  
  
 Время ожидания для перегрузок метода <xref:System.Threading.Monitor.Wait%2A> позволяет ожидающим потокам перейти в очередь готовности.  
  
 Класс <xref:System.Threading.Monitor> может предоставить блокировку в нескольких доменах приложений, если объект, используемый для блокировки, является производным от <xref:System.MarshalByRefObject>.  
  
 Класс <xref:System.Threading.Monitor> реализует сходство потоков.  То есть поток, вошедший в этот класс, должен выйти посредством вызова метода <xref:System.Threading.Monitor.Exit%2A> или <xref:System.Threading.Monitor.Wait%2A>.  
  
 Класс <xref:System.Threading.Monitor> не поддерживает создание экземпляров.  Его методы являются статическими \(`Shared` в Visual Basic\) и работают с созданным экземпляром заблокированного объекта.  
  
 Обзор концепции см. в разделе [Мониторы](../Topic/Monitors.md).  
  
#### Класс Mutex  
 Потоки запрашивают <xref:System.Threading.Mutex> путем вызова перегрузки его метода <xref:System.Threading.WaitHandle.WaitOne%2A>.  Перегрузки со временем ожидания предоставляются для освобождения потоков после определенного времени ожидания.  В отличие от класса <xref:System.Threading.Monitor> мьютекс может быть или локальным, или глобальным.  Глобальные мьютексы, также называемые именованными мьютексами, видны в операционной системе и могут использоваться для синхронизации потоков в различных доменах приложений или процессах.  Локальные мьютексы происходят от <xref:System.MarshalByRefObject> и могут использоваться за границами домена приложения.  
  
 Кроме того, <xref:System.Threading.Mutex> происходит от <xref:System.Threading.WaitHandle>, что означает возможность его использования в сигнальных механизмах, предоставленных <xref:System.Threading.WaitHandle>, таких как методы <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> и <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  
  
 Как и класс <xref:System.Threading.Monitor>, класс <xref:System.Threading.Mutex> поддерживает сходство потоков.  В отличие от <xref:System.Threading.Monitor> класс <xref:System.Threading.Mutex> поддерживает создание экземпляров.  
  
 Обзор концепции см. в разделе [Mutexes](../../../docs/standard/threading/mutexes.md).  
  
#### Класс SpinLock  
 Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно использовать класс <xref:System.Threading.SpinLock>, когда накладные расходы, вызванные использованием <xref:System.Threading.Monitor>, ухудшают быстродействие.  Когда объект <xref:System.Threading.SpinLock> обнаруживает блокированную критическую секцию, он просто входит в цикл, пока блокировка не станет доступной.  Если блокировка сохраняется в течение очень короткого времени, вхождение в цикл может обеспечить лучшее быстродействие, чем блокировка.  Но если блокировка сохраняется дольше нескольких десятков тактов процессора, <xref:System.Threading.SpinLock> работает так же хорошо, как и <xref:System.Threading.Monitor>, но использует больше тактов процессора и, таким образом, может понизить быстродействие других потоков или процессов.  
  
### Другие блокировки  
 Блокировки не обязательно должны быть монопольными.  Часто бывает полезным разрешить одновременный доступ к ресурсу ограниченному количеству потоков.  Семафоры и блокировки чтения и записи предназначены для управления доступом к ресурсу в пуле.  
  
#### Класс ReaderWriterLock  
 Класс <xref:System.Threading.ReaderWriterLockSlim> предназначен для тех случаев, когда поток, изменяющий данные, \(модуль записи\) должен иметь монопольный доступ к ресурсу.  Если модуль записи не активен, любое количество модулей чтения может получить доступ к ресурсу \(например, путем вызова метода <xref:System.Threading.ReaderWriterLockSlim.EnterReadLock%2A>\).  Если поток запрашивает монопольный доступ \(например, путем вызова метода <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A>\), последующие запросы модуля чтения блокируются до того момента, как все существующие модули чтения не освободят блокировку, а модуль записи не установит и не снимет блокировку.  
  
 Класс <xref:System.Threading.ReaderWriterLockSlim> реализует сходство потоков.  
  
 Обзор концепции см. в разделе [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md).  
  
#### Класс Semaphore  
 Класс <xref:System.Threading.Semaphore> разрешает доступ к ресурсу определенному количеству потоков.  Дополнительные потоки, запрашивающие ресурс, блокируются до освобождения потоком семафора.  
  
 Как и класс <xref:System.Threading.Mutex>, класс <xref:System.Threading.Semaphore> является производным от класса <xref:System.Threading.WaitHandle>.  Кроме того, как и класс <xref:System.Threading.Mutex>, класс <xref:System.Threading.Semaphore> может быть локальным или глобальным.  Он может использоваться за пределами границ домена приложения.  
  
 В отличие от классов <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> и <xref:System.Threading.ReaderWriterLock>, класс <xref:System.Threading.Semaphore> не поддерживает сходство потоков.  Это означает, что его можно использовать в сценариях, в которых один поток получает семафор, а другой поток освобождает его.  
  
 Обзор концепции см. в разделе [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md).  
  
 <xref:System.Threading.SemaphoreSlim?displayProperty=fullName> — это упрощенный семафор для синхронизации в границах одного процесса.  
  
 [К началу](#top)  
  
<a name="signaling"></a>   
## Сигнальный NaN  
 Самым простым способом ожидания сигнала от другого потока является вызов метода <xref:System.Threading.Thread.Join%2A>, который блокирует поток до завершения другого потока.  У метода <xref:System.Threading.Thread.Join%2A> есть две перегрузки, которые позволяют блокированному потоку освободиться от ожидания по истечении заданного времени.  
  
 Дескрипторы ожидания предоставляют более полный набор возможностей ожидания и сигнализации.  
  
### Дескрипторы ожидания  
 Дескрипторы ожидания являются производными от класса <xref:System.Threading.WaitHandle>, который, в свою очередь, является производным от <xref:System.MarshalByRefObject>.  Поэтому дескрипторы ожидания можно использовать для синхронизации действий потоков за границами доменов приложений.  
  
 Потоки блокируются при дескрипторах ожидания посредством вызова метода экземпляра <xref:System.Threading.WaitHandle.WaitOne%2A> или одного из статических методов <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> или <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  Способ их освобождения зависит от того, какой метод был вызван, а также от типа дескрипторов ожидания.  
  
 Обзор концепции см. в разделе [Wait Handles](../Topic/Wait%20Handles.md).  
  
#### Дескрипторы ожидания событий  
 Дескрипторы ожидания событий включают класс <xref:System.Threading.EventWaitHandle> и его производные классы <xref:System.Threading.AutoResetEvent> и <xref:System.Threading.ManualResetEvent>.  Потоки освобождаются от дескриптора ожидания событий, если этот дескриптор получает сигнал посредством вызова метода <xref:System.Threading.EventWaitHandle.Set%2A> или с помощью метода <xref:System.Threading.WaitHandle.SignalAndWait%2A>.  
  
 Дескрипторы ожидания событий или сбрасывают себя автоматически, как турникет, разрешающий только один поток при каждом сигнале, или должны быть сброшены вручную, как ворота, которые закрыты до получения сигнала, а затем открыты, пока их кто\-нибудь не закроет.  В соответствии с их именами классы <xref:System.Threading.AutoResetEvent> и <xref:System.Threading.ManualResetEvent> представляют соответственно первый и второй подходы.  <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> — это упрощенное событие для синхронизации в границах одного процесса.  
  
 Дескриптор <xref:System.Threading.EventWaitHandle> может представлять любой тип события и может быть локальным или глобальным.  Производные классы <xref:System.Threading.AutoResetEvent> и <xref:System.Threading.ManualResetEvent> всегда являются локальными.  
  
 Дескрипторы ожидания событий не поддерживают сходство потоков.  Любой поток может подать сигнал дескриптору ожидания событий.  
  
 Обзор концепции см. в разделе [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).  
  
#### Классы Mutex и Semaphore  
 Так как классы <xref:System.Threading.Mutex> и <xref:System.Threading.Semaphore> являются производными от класса <xref:System.Threading.WaitHandle>, они могут использоваться со статическими методами класса <xref:System.Threading.WaitHandle>.  Например, поток может использовать метод <xref:System.Threading.WaitHandle.WaitAll%2A> для ожидания выполнения всех трех условий: подан сигнал дескриптору <xref:System.Threading.EventWaitHandle>, освобожден мьютекс <xref:System.Threading.Mutex> и сброшен семафор <xref:System.Threading.Semaphore>.  Также поток может использовать метод <xref:System.Threading.WaitHandle.WaitAny%2A> для ожидания выполнения одного из этих условий.  
  
 Для классов <xref:System.Threading.Mutex> и <xref:System.Threading.Semaphore> получение сигнала означает освобождение.  Если в качестве первого аргумента метода <xref:System.Threading.WaitHandle.SignalAndWait%2A> используется любой из этих типов, он освобождается.  В случае класса <xref:System.Threading.Mutex>, поддерживающего сходство потоков, исключение создается, если вызывающий поток не имеет собственного мьютекса.  Как отмечалось ранее, семафоры не поддерживают сходство потоков.  
  
#### Барьер  
 Класс <xref:System.Threading.Barrier> предоставляет способ циклической синхронизации нескольких потоков, позволяющий заблокировать их все в одной точке и дождаться завершения всех остальных потоков.  Барьер полезен, когда одному или нескольким потокам для перехода к следующему этапу алгоритма требуются результаты выполнения другого потока.  Подробнее см. в разделе [Barrier](../../../docs/standard/threading/barrier.md).  
  
 [К началу](#top)  
  
<a name="lightweight_synchronization_types"></a>   
## Типы упрощенной синхронизации  
 Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], можно использовать примитивы синхронизации, обеспечивающие высокое быстродействие путем предотвращения по возможности ресурсоемкого использования объектов ядра Win32, таких как дескрипторы ожидания.  Обычно эти типы следует использовать при небольшом времени ожидания и только после того, как исходные типы синхронизации были испытаны и признаны негодными.  Эти упрощенные типы нельзя использовать в сценариях, требующих взаимодействия между процессами.  
  
-   Семафор <xref:System.Threading.SemaphoreSlim?displayProperty=fullName> является упрощенной версией семафора <xref:System.Threading.Semaphore?displayProperty=fullName>.  
  
-   Семафор <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> является упрощенной версией семафора <xref:System.Threading.ManualResetEvent?displayProperty=fullName>.  
  
-   Класс <xref:System.Threading.CountdownEvent?displayProperty=fullName> представляет событие, возникающее, когда его счетчик становится равным нулю.  
  
-   Барьер <xref:System.Threading.Barrier?displayProperty=fullName> позволяет синхронизировать друг с другом несколько потоков без управления со стороны главного потока.  Барьер не позволяет каждому из потоков продолжить выполнение, пока все потоки не достигнут заданной точки.  
  
 [К началу](#top)  
  
<a name="spinwait"></a>   
## SpinWait  
 Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], можно использовать структуру <xref:System.Threading.SpinWait?displayProperty=fullName>, когда потоку нужно дождаться возникновения события или выполнения условия, но, когда предполагается, что фактическое время ожидания будет меньше требуемого времени ожидания, требуется применить дескриптор ожидания или другой способ блокировки текущего потока.  Используя <xref:System.Threading.SpinWait>, можно задать короткий интервал времени для цикла ожидания, а затем вернуть управление \(например, с помощью ожидания или спящего режима\), только если условие не было выполнено в течение заданного времени.  
  
 [К началу](#top)  
  
<a name="interlocked_operations"></a>   
## Блокируемые операции  
 Блокируемые операции — это простые атомарные операции, выполняемые в области памяти статическими методами класса <xref:System.Threading.Interlocked>.  Эти атомарные операции включают добавление, увеличение и уменьшение, обмен, условный обмен в зависимости от сравнения, а также операции чтения для 64\-разрядных значений на 32\-разрядных платформах.  
  
> [!NOTE]
>  Гарантия атомарности ограничена отдельными операциями. Если необходимо выполнить несколько операций в одном блоке, следует использовать более весомые механизмы синхронизации.  
  
 Несмотря на то что ни одна из этих операций не является блокировкой или сигналом, они могут использоваться для создания блокировок и сигналов.  Так как блокируемые операции являются собственными операциями ОС Windows, они выполняются очень быстро.  
  
 Блокируемые операции можно использовать с энергонезависимой памятью для написания приложений, демонстрирующих эффективную параллельную работу без блокировок.  Но для них требуется сложное низкоуровневое программирование, поэтому для большинства задач оптимальным выбором оказываются простые блокировки.  
  
 Обзор концепции см. в разделе [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md).  
  
## См. также  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)   
 [Мониторы](../Topic/Monitors.md)   
 [Mutexes](../../../docs/standard/threading/mutexes.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)   
 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)   
 [Barrier](../../../docs/standard/threading/barrier.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [SpinLock](../../../docs/standard/threading/spinlock.md)