---
title: "Основы управляемых потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 035834959aa5f9340727327b22cae93b3f21b056
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="managed-threading-basics"></a><span data-ttu-id="7ac6b-102">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="7ac6b-102">Managed Threading Basics</span></span>
<span data-ttu-id="7ac6b-103">Первые пять тем этого раздела помогут вам понять, в каких случаях уместно применять управляемые потоки, и предоставят описания их основных компонентов.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="7ac6b-104">Сведения о классах, которые предоставляют дополнительные возможности, вы найдете в статьях [Объекты и функциональные возможности работы с потоками](../../../docs/standard/threading/threading-objects-and-features.md) и [Обзор примитивов синхронизации](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="7ac6b-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="7ac6b-105">Остальные темы этого раздела посвящены дополнительным возможностям, включая взаимодействие управляемых потоков с операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ac6b-106">На платформе [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] библиотека параллельных задач и PLINQ предоставляют интерфейсы API для поддержки параллелизма задач и данных в многопоточных программах.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="7ac6b-107">Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="7ac6b-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ac6b-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7ac6b-108">In This Section</span></span>  
 [<span data-ttu-id="7ac6b-109">Потоки и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="7ac6b-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="7ac6b-110">Преимущества и недостатки использования нескольких потоков, а также описание сценариев, в которых целесообразно создавать потоки или использовать пул потоков.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="7ac6b-111">Исключения в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="7ac6b-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="7ac6b-112">Описание поведения необработанных исключений в потоках для разных версий платформы .NET Framework с особым вниманием к тем ситуациям, в которых они приведут к завершению работы приложения.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="7ac6b-113">Синхронизация данных для многопоточности</span><span class="sxs-lookup"><span data-stu-id="7ac6b-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="7ac6b-114">Описание стратегий синхронизации данных в классах, которые следует применять при работе с несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="7ac6b-115">Состояния управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="7ac6b-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="7ac6b-116">Описание основных состояний потоков и действий, позволяющих определить, выполняется ли поток.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="7ac6b-117">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="7ac6b-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="7ac6b-118">Описание различий между основными и фоновыми потоками.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="7ac6b-119">Управляемые и неуправляемые потоки в Windows</span><span class="sxs-lookup"><span data-stu-id="7ac6b-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="7ac6b-120">Описание соотношений между управляемыми и неуправляемыми потоками, список управляемых эквивалентов для работы с API-интерфейсами потоков в Windows, описание взаимодействий между подразделениями COM и управляемыми потоками.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="7ac6b-121">Метод Thread.Suspend, сборка мусора и безопасные точки</span><span class="sxs-lookup"><span data-stu-id="7ac6b-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="7ac6b-122">Описание приостановки потоков и сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="7ac6b-123">Локальное хранилище потока: статические поля потока и области данных</span><span class="sxs-lookup"><span data-stu-id="7ac6b-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="7ac6b-124">Описание механизмов хранения для отдельных потоков.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="7ac6b-125">Отмена в управляемых потоках</span><span class="sxs-lookup"><span data-stu-id="7ac6b-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="7ac6b-126">Описание процесса отмены асинхронных или долго выполняющихся синхронных операций с использованием маркера отмены.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7ac6b-127">Ссылка</span><span class="sxs-lookup"><span data-stu-id="7ac6b-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="7ac6b-128">Справочная документация по классу **Thread**, который представляет управляемый поток вне зависимости от того, был ли он получен из неуправляемого кода или создан в управляемом приложении.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="7ac6b-129">Описание безопасного подхода к многопоточности при работе с объектами пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7ac6b-130">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ac6b-130">Related Sections</span></span>  
 [<span data-ttu-id="7ac6b-131">Обзор примитивов синхронизации</span><span class="sxs-lookup"><span data-stu-id="7ac6b-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="7ac6b-132">Описание управляемых классов, которые применяются для синхронизации действий в нескольких потоках.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="7ac6b-133">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="7ac6b-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="7ac6b-134">Описание распространенных проблем с многопоточностью и стратегий для предотвращения проблем.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="7ac6b-135">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="7ac6b-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="7ac6b-136">Описание библиотеки параллельных задач и PLINQ, которые существенно упрощают создание асинхронных и многопоточных приложений .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ac6b-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
