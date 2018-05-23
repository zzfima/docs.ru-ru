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
ms.openlocfilehash: 02f88faab6ddbaa026e73ad61bc63fbe8e5e00ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="e5d9a-102">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="e5d9a-102">Threading Objects and Features</span></span>
<span data-ttu-id="e5d9a-103">Платформа .NET Framework предоставляет ряд объектов, которые помогают создавать многопоточные приложения и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="e5d9a-104">Управляемые потоки представлены классом <xref:System.Threading.Thread>.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="e5d9a-105">Класс <xref:System.Threading.ThreadPool> позволяет легко создавать многопоточные фоновые задачи и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="e5d9a-106">Класс <xref:System.ComponentModel.BackgroundWorker> используется в тех же целях для задач, которые взаимодействуют с пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="e5d9a-107">Класс <xref:System.Threading.Timer> выполняет фоновые задачи через определенные интервалы.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="e5d9a-108">Кроме того, существует ряд классов, которые синхронизируют действия потоков, включая классы <xref:System.Threading.Semaphore> и <xref:System.Threading.EventWaitHandle>, появившиеся в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e5d9a-109">Возможности этих классов сравниваются в разделе [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="e5d9a-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5d9a-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e5d9a-110">In This Section</span></span>  
 [<span data-ttu-id="e5d9a-111">Пул управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="e5d9a-111">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)  
 <span data-ttu-id="e5d9a-112">Описывается класс **ThreadPool**, который позволяет запросить выполнение задачи потоком без необходимости управлять потоком самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 [<span data-ttu-id="e5d9a-113">Таймеры</span><span class="sxs-lookup"><span data-stu-id="e5d9a-113">Timers</span></span>](../../../docs/standard/threading/timers.md)  
 <span data-ttu-id="e5d9a-114">Описывается использование объекта **Timer** для указания делегата, вызываемого в указанное время.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-114">Explains how to use a **Timer** to specify a delegate to be called at a specified time.</span></span>  
  
 [<span data-ttu-id="e5d9a-115">Мониторы</span><span class="sxs-lookup"><span data-stu-id="e5d9a-115">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 <span data-ttu-id="e5d9a-116">Описывается использование класса **Monitor** для синхронизации доступа к члену или создания собственных типов управления потоками.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 [<span data-ttu-id="e5d9a-117">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="e5d9a-117">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="e5d9a-118">Описывается класс <xref:System.Threading.WaitHandle> — абстрактный базовый класс для дескрипторов ожидания событий, мьютексов и семафоров, который обеспечивает ожидание нескольких событий синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="e5d9a-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="e5d9a-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="e5d9a-120">Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 [<span data-ttu-id="e5d9a-121">Мьютексы</span><span class="sxs-lookup"><span data-stu-id="e5d9a-121">Mutexes</span></span>](../../../docs/standard/threading/mutexes.md)  
 <span data-ttu-id="e5d9a-122">Описывается использование объекта <xref:System.Threading.Mutex>для синхронизации доступа к объекту или создания собственных механизмов синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 [<span data-ttu-id="e5d9a-123">Блокируемые операции</span><span class="sxs-lookup"><span data-stu-id="e5d9a-123">Interlocked Operations</span></span>](../../../docs/standard/threading/interlocked-operations.md)  
 <span data-ttu-id="e5d9a-124">Описывается использование класса <xref:System.Threading.Interlocked> для пошагового увеличения или уменьшения значения и сохранения значения в одной атомарной операции.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 [<span data-ttu-id="e5d9a-125">Блокировки чтения и записи</span><span class="sxs-lookup"><span data-stu-id="e5d9a-125">Reader-Writer Locks</span></span>](../../../docs/standard/threading/reader-writer-locks.md)  
 <span data-ttu-id="e5d9a-126">Определяет блокировку, которая реализует семантику однократной записи и многократного чтения.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 [<span data-ttu-id="e5d9a-127">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="e5d9a-127">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <span data-ttu-id="e5d9a-128">Описываются объекты <xref:System.Threading.Semaphore> и способы их использования для управления доступом к ограниченным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 [<span data-ttu-id="e5d9a-129">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="e5d9a-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="e5d9a-130">Сравниваются возможности классов .NET Framework, предоставляемых для блокировки и синхронизации управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 [<span data-ttu-id="e5d9a-131">Barrier</span><span class="sxs-lookup"><span data-stu-id="e5d9a-131">Barrier</span></span>](../../../docs/standard/threading/barrier.md)  
 <span data-ttu-id="e5d9a-132">Описываются объекты <xref:System.Threading.Barrier>, реализующие шаблон барьера для координации потоков при выполнении поэтапных операций.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="e5d9a-133">SpinLock</span><span class="sxs-lookup"><span data-stu-id="e5d9a-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="e5d9a-134">Описывается класс <xref:System.Threading.SpinLock> — упрощенная альтернатива классу Monitor для определенных низкоуровневых сценариев.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="e5d9a-135">SpinWait</span><span class="sxs-lookup"><span data-stu-id="e5d9a-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="e5d9a-136">Описывается <xref:System.Threading.SpinWait> — низкоуровневый примитив синхронизации, выполняющий цикличную работу в режиме занятости до инициирования ожидания ядра.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e5d9a-137">Ссылка</span><span class="sxs-lookup"><span data-stu-id="e5d9a-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="e5d9a-138">Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="e5d9a-139">Активация фоновых задач, которые взаимодействуют с пользовательским интерфейсом посредством событий, возникающих в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5d9a-140">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e5d9a-140">Related Sections</span></span>  
 [<span data-ttu-id="e5d9a-141">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="e5d9a-141">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="e5d9a-142">Описывается использование пула потоков портами асинхронного завершения ввода-вывода для запроса обработки только после завершения операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="e5d9a-143">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="e5d9a-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="e5d9a-144">Описывается рекомендуемый подход к многопоточному программированию в [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="e5d9a-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
