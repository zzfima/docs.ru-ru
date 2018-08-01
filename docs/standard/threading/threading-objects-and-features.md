---
title: Объекты и функциональные возможности работы с потоками
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d689aeb91ad79b776c3b93c1809ec46947ea60b
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874791"
---
# <a name="threading-objects-and-features"></a>Объекты и функциональные возможности работы с потоками
Платформа .NET Framework предоставляет ряд объектов, которые помогают создавать многопоточные приложения и управлять ими. Управляемые потоки представлены классом <xref:System.Threading.Thread>. Класс <xref:System.Threading.ThreadPool> позволяет легко создавать многопоточные фоновые задачи и управлять ими. Класс <xref:System.ComponentModel.BackgroundWorker> используется в тех же целях для задач, которые взаимодействуют с пользовательским интерфейсом. Класс <xref:System.Threading.Timer> выполняет фоновые задачи через определенные интервалы.  
  
 Кроме того, существует ряд классов, которые синхронизируют действия потоков, включая классы <xref:System.Threading.Semaphore> и <xref:System.Threading.EventWaitHandle>, появившиеся в .NET Framework версии 2.0. Возможности этих классов сравниваются в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пул управляемых потоков](../../../docs/standard/threading/the-managed-thread-pool.md)  
 Описывается класс **ThreadPool**, который позволяет запросить выполнение задачи потоком без необходимости управлять потоком самостоятельно.  
  
 [Таймеры](../../../docs/standard/threading/timers.md)  
 Описывает таймеры, которые можно использовать в многопоточной среде.  
  
 [Мониторы](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 Описывается использование класса **Monitor** для синхронизации доступа к члену или создания собственных типов управления потоками.  
  
 [Дескрипторы ожидания](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 Описывается класс <xref:System.Threading.WaitHandle> — абстрактный базовый класс для дескрипторов ожидания событий, мьютексов и семафоров, который обеспечивает ожидание нескольких событий синхронизации.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.  
  
 [Мьютексы](../../../docs/standard/threading/mutexes.md)  
 Описывается использование объекта <xref:System.Threading.Mutex>для синхронизации доступа к объекту или создания собственных механизмов синхронизации.  
  
 [Блокируемые операции](../../../docs/standard/threading/interlocked-operations.md)  
 Описывается использование класса <xref:System.Threading.Interlocked> для пошагового увеличения или уменьшения значения и сохранения значения в одной атомарной операции.  
  
 [Блокировки чтения и записи](../../../docs/standard/threading/reader-writer-locks.md)  
 Определяет блокировку, которая реализует семантику однократной записи и многократного чтения.  
  
 [Классы Semaphore и SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 Описываются объекты <xref:System.Threading.Semaphore> и способы их использования для управления доступом к ограниченным ресурсам.  
  
 [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 Сравниваются возможности классов .NET Framework, предоставляемых для блокировки и синхронизации управляемых потоков.  
  
 [Barrier](../../../docs/standard/threading/barrier.md)  
 Описываются объекты <xref:System.Threading.Barrier>, реализующие шаблон барьера для координации потоков при выполнении поэтапных операций.  
  
 [SpinLock](../../../docs/standard/threading/spinlock.md)  
 Описывается класс <xref:System.Threading.SpinLock> — упрощенная альтернатива классу Monitor для определенных низкоуровневых сценариев.  
  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 Описывается <xref:System.Threading.SpinWait> — низкоуровневый примитив синхронизации, выполняющий цикличную работу в режиме занятости до инициирования ожидания ядра.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Threading.Thread>  
 Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Активация фоновых задач, которые взаимодействуют с пользовательским интерфейсом посредством событий, возникающих в потоке пользовательского интерфейса.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md)  
 Описывается использование пула потоков портами асинхронного завершения ввода-вывода для запроса обработки только после завершения операции ввода-вывода.  
  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Описывается рекомендуемый подход к многопоточному программированию в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и более поздних версиях.
