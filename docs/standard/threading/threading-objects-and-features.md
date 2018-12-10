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
ms.openlocfilehash: 9a355c2e996ddb00dad804dfeb22987923d91aa6
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144524"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="3fda4-102">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="3fda4-102">Threading objects and features</span></span>

<span data-ttu-id="3fda4-103">Вместе с классом <xref:System.Threading.Thread?displayProperty=nameWithType> .NET предоставляет ряд классов для разработки многопоточных приложений.</span><span class="sxs-lookup"><span data-stu-id="3fda4-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="3fda4-104">В следующих статьях приведены общие сведения об этих классах:</span><span class="sxs-lookup"><span data-stu-id="3fda4-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="3fda4-105">Заголовок</span><span class="sxs-lookup"><span data-stu-id="3fda4-105">Title</span></span>|<span data-ttu-id="3fda4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3fda4-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3fda4-107">Пул управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="3fda4-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="3fda4-108">Описание класса <xref:System.Threading.ThreadPool?displayProperty=nameWithType>, который предоставляет пул рабочих потоков, управляемых .NET.</span><span class="sxs-lookup"><span data-stu-id="3fda4-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="3fda4-109">Таймеры</span><span class="sxs-lookup"><span data-stu-id="3fda4-109">Timers</span></span>](timers.md)|<span data-ttu-id="3fda4-110">Описывает таймеры .NET, которые можно использовать в многопоточной среде.</span><span class="sxs-lookup"><span data-stu-id="3fda4-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="3fda4-111">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="3fda4-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="3fda4-112">Описывает типы, которые можно использовать для синхронизации доступа к общему ресурсу или для управления взаимодействием потоков.</span><span class="sxs-lookup"><span data-stu-id="3fda4-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="3fda4-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="3fda4-113">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)|<span data-ttu-id="3fda4-114">Описываются управляемые дескрипторы ожидания событий, которые используются для синхронизации действий потоков путем отправки и ожидания сигналов.</span><span class="sxs-lookup"><span data-stu-id="3fda4-114">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>|
|[<span data-ttu-id="3fda4-115">Мьютексы</span><span class="sxs-lookup"><span data-stu-id="3fda4-115">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="3fda4-116">Описывает <xref:System.Threading.Mutex?displayProperty=nameWithType>, который предоставляет монопольный доступ к общему ресурсу.</span><span class="sxs-lookup"><span data-stu-id="3fda4-116">Describes <xref:System.Threading.Mutex?displayProperty=nameWithType>, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="3fda4-117">Классы Semaphore и SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="3fda4-117">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="3fda4-118">Описывает класс 3<xref:System.Threading.Semaphore?displayProperty=nameWithType>, ограничивающий число потоков, которые могут одновременно обращаться к ресурсу или пулу ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3fda4-118">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="3fda4-119">Barrier</span><span class="sxs-lookup"><span data-stu-id="3fda4-119">Barrier</span></span>](barrier.md)|<span data-ttu-id="3fda4-120">Описывает класс <xref:System.Threading.Barrier?displayProperty=nameWithType>, реализующий шаблон барьера для координации потоков при выполнении поэтапных операций.</span><span class="sxs-lookup"><span data-stu-id="3fda4-120">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class that implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="3fda4-121">SpinLock</span><span class="sxs-lookup"><span data-stu-id="3fda4-121">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="3fda4-122">Описывает структуру <xref:System.Threading.SpinLock?displayProperty=nameWithType>, упрощенную альтернативу классу <xref:System.Threading.Monitor?displayProperty=nameWithType> для определенных низкоуровневых сценариев блокировки.</span><span class="sxs-lookup"><span data-stu-id="3fda4-122">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="3fda4-123">SpinWait</span><span class="sxs-lookup"><span data-stu-id="3fda4-123">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="3fda4-124">Описывает структуру <xref:System.Threading.SpinWait?displayProperty=nameWithType>, которая обеспечивает поддержку ожидания на основе холостых циклов.</span><span class="sxs-lookup"><span data-stu-id="3fda4-124">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3fda4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3fda4-125">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="3fda4-126">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="3fda4-126">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="3fda4-127">Asynchronous File I/O</span><span class="sxs-lookup"><span data-stu-id="3fda4-127">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="3fda4-128">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="3fda4-128">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="3fda4-129">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="3fda4-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
