---
title: Объекты и функциональные возможности работы с потоками
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f25609bc3c4dd829c66a1a4514b7f1121f9c0909
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759032"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="d2d0e-102">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="d2d0e-102">Threading objects and features</span></span>

<span data-ttu-id="d2d0e-103">Вместе с классом <xref:System.Threading.Thread?displayProperty=nameWithType> .NET предоставляет ряд классов для разработки многопоточных приложений.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="d2d0e-104">В следующих статьях приведены общие сведения об этих классах:</span><span class="sxs-lookup"><span data-stu-id="d2d0e-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="d2d0e-105">Заголовок</span><span class="sxs-lookup"><span data-stu-id="d2d0e-105">Title</span></span>|<span data-ttu-id="d2d0e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d2d0e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d2d0e-107">Пул управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="d2d0e-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="d2d0e-108">Описание класса <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, который предоставляет пул рабочих потоков, управляемых .NET.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="d2d0e-109">Таймеры</span><span class="sxs-lookup"><span data-stu-id="d2d0e-109">Timers</span></span>](timers.md)|<span data-ttu-id="d2d0e-110">Описывает таймеры .NET, которые можно использовать в многопоточной среде.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="d2d0e-111">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="d2d0e-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="d2d0e-112">Описывает типы, которые можно использовать для синхронизации доступа к общему ресурсу или для управления взаимодействием потоков.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="d2d0e-113">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="d2d0e-113">EventWaitHandle</span></span>](eventwaithandle.md)|<span data-ttu-id="d2d0e-114">Описывает класс <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>, который представляет событие синхронизации потока.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-114">Describes the <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class, which represents a thread synchronization event.</span></span>|
|[<span data-ttu-id="d2d0e-115">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="d2d0e-115">CountdownEvent</span></span>](countdownevent.md)|<span data-ttu-id="d2d0e-116">Описывает класс <xref:System.Threading.CountdownEvent?displayProperty=nameWithType>, который представляет событие синхронизации потока, задаваемое при отсчете до нуля.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-116">Describes the <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class, which represents a thread synchronization event that becomes set when its count is zero.</span></span>|
|[<span data-ttu-id="d2d0e-117">Мьютексы</span><span class="sxs-lookup"><span data-stu-id="d2d0e-117">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="d2d0e-118">Описывает класс <xref:System.Threading.Mutex?displayProperty=nameWithType>, который предоставляет монопольный доступ к общему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-118">Describes the <xref:System.Threading.Mutex?displayProperty=nameWithType> class, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="d2d0e-119">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="d2d0e-119">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="d2d0e-120">Описывает класс 3<xref:System.Threading.Semaphore?displayProperty=nameWithType>, ограничивающий число потоков, которые могут одновременно обращаться к ресурсу или пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-120">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="d2d0e-121">Barrier</span><span class="sxs-lookup"><span data-stu-id="d2d0e-121">Barrier</span></span>](barrier.md)|<span data-ttu-id="d2d0e-122">Описывает класс <xref:System.Threading.Barrier?displayProperty=nameWithType>, реализующий шаблон барьера для координации потоков при выполнении поэтапных операций.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-122">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class, which implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="d2d0e-123">SpinLock</span><span class="sxs-lookup"><span data-stu-id="d2d0e-123">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="d2d0e-124">Описывает структуру <xref:System.Threading.SpinLock?displayProperty=nameWithType>, упрощенную альтернативу классу <xref:System.Threading.Monitor?displayProperty=nameWithType> для определенных низкоуровневых сценариев блокировки.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-124">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="d2d0e-125">SpinWait</span><span class="sxs-lookup"><span data-stu-id="d2d0e-125">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="d2d0e-126">Описывает структуру <xref:System.Threading.SpinWait?displayProperty=nameWithType>, которая обеспечивает поддержку ожидания на основе холостых циклов.</span><span class="sxs-lookup"><span data-stu-id="d2d0e-126">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d2d0e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d2d0e-127">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="d2d0e-128">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="d2d0e-128">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="d2d0e-129">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="d2d0e-129">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="d2d0e-130">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="d2d0e-130">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="d2d0e-131">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="d2d0e-131">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
