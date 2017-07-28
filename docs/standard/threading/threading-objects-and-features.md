---
title: "Threading Objects and Features | Microsoft Docs"
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
  - "threading [.NET Framework], features"
  - "managed threading"
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Threading Objects and Features
Платформа .NET Framework предоставляет ряд объектов, которые помогают создавать многопоточные приложения и управлять ими.  Управляемые потоки представлены классом <xref:System.Threading.Thread>.  Класс <xref:System.Threading.ThreadPool> позволяет легко создавать многопоточные фоновые задачи и управлять ими.  Класс <xref:System.ComponentModel.BackgroundWorker> используется в тех же целях для задач, которые взаимодействуют с пользовательским интерфейсом.  Класс <xref:System.Threading.Timer> выполняет фоновые задачи через определенные интервалы.  
  
 Кроме того, существует ряд классов, которые синхронизируют действия потоков, включая классы <xref:System.Threading.Semaphore> и <xref:System.Threading.EventWaitHandle>, появившиеся в .NET Framework версии 2.0.  Возможности этих классов сравниваются в разделе [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## В этом подразделе  
 [The Managed Thread Pool](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Описывается класс **ThreadPool**, который позволяет запросить выполнение задачи потоком без необходимости управлять потоком самостоятельно.  
  
 [Timers](../../../docs/standard/threading/timers.md)  
 Описывается использование объекта **Timer** для указания делегата, вызываемого в указанное время.  
  
 [Мониторы](../Topic/Monitors.md)  
 Описывается использование класса **Monitor** для синхронизации доступа к члену или создания собственных типов управления потоками.  
  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 Описывается класс <xref:System.Threading.WaitHandle> — абстрактный базовый класс для дескрипторов ожидания событий, мьютексов и семафоров, который обеспечивает ожидание нескольких событий синхронизации.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.  
  
 [Mutexes](../../../docs/standard/threading/mutexes.md)  
 Описывается использование объекта <xref:System.Threading.Mutex>для синхронизации доступа к объекту или создания собственных механизмов синхронизации.  
  
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)  
 Описывается использование класса <xref:System.Threading.Interlocked> для пошагового увеличения или уменьшения значения и сохранения значения в одной атомарной операции.  
  
 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)  
 Определяет блокировку, которая реализует семантику однократной записи и многократного чтения.  
  
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 Описываются объекты <xref:System.Threading.Semaphore> и способы их использования для управления доступом к ограниченным ресурсам.  
  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Сравниваются возможности классов .NET Framework, предоставляемых для блокировки и синхронизации управляемых потоков.  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 Описываются объекты <xref:System.Threading.Barrier>, реализующие шаблон барьера для координации потоков при выполнении поэтапных операций.  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 Описывается класс <xref:System.Threading.SpinLock> — упрощенная альтернатива классу Monitor для определенных низкоуровневых сценариев.  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 Описывается <xref:System.Threading.SpinWait> — низкоуровневый примитив синхронизации, выполняющий цикличную работу в режиме занятости до инициирования ожидания ядра.  
  
## Ссылка  
 <xref:System.Threading.Thread>  
 Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Активация фоновых задач, которые взаимодействуют с пользовательским интерфейсом посредством событий, возникающих в потоке пользовательского интерфейса.  
  
## Связанные подразделы  
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)  
 Описывается использование пула потоков портами асинхронного завершения ввода\-вывода для запроса обработки только после завершения операции ввода\-вывода.  
  
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Описывается рекомендуемый подход к многопоточному программированию в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и более поздних версиях.