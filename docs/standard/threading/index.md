---
title: Управляемая поточность
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
ms.openlocfilehash: c5ca102dc98e50067d39d2f0c51a6ff75e342e9f
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588657"
---
# <a name="managed-threading"></a><span data-ttu-id="075b3-102">Управляемая поточность</span><span class="sxs-lookup"><span data-stu-id="075b3-102">Managed Threading</span></span>
<span data-ttu-id="075b3-103">При разработке для компьютеров как с одним, так и с несколькими процессорами, необходимо, чтобы приложение обеспечивало наиболее эффективное взаимодействие с пользователем, даже если в приложении выполняются другие задачи.</span><span class="sxs-lookup"><span data-stu-id="075b3-103">Whether you are developing for computers with one processor or several, you want your application to provide the most responsive interaction with the user, even if the application is currently doing other work.</span></span> <span data-ttu-id="075b3-104">Использование нескольких потоков выполнения — это один из способов обеспечить в приложении возможность реагирования на действия пользователя при одновременном использовании процессора для выполнения задач между появлением или даже во время появления событий пользователя.</span><span class="sxs-lookup"><span data-stu-id="075b3-104">Using multiple threads of execution is one of the most powerful ways to keep your application responsive to the user and at the same time make use of the processor in between or even during user events.</span></span> <span data-ttu-id="075b3-105">Хотя в этом разделе приведены основные сведения о потоковом выполнении, здесь также рассматриваются принципы работы управляемых потоков и их использование.</span><span class="sxs-lookup"><span data-stu-id="075b3-105">While this section introduces the basic concepts of threading, it focuses on managed threading concepts and using managed threading.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="075b3-106">Начиная с .NET Framework 4, многопоточное программирование значительно упростилось благодаря классам <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md), новым классам параллельных коллекций из пространства имен <xref:System.Collections.Concurrent?displayProperty=nameWithType> и новой модели программирования, которая вместо потоков использует концепцию задач.</span><span class="sxs-lookup"><span data-stu-id="075b3-106">Starting with the .NET Framework 4, multithreaded programming is greatly simplified with the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> classes, [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md), new concurrent collection classes in the <xref:System.Collections.Concurrent?displayProperty=nameWithType> namespace, and a new programming model that is based on the concept of tasks rather than threads.</span></span> <span data-ttu-id="075b3-107">Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="075b3-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="075b3-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="075b3-108">In This Section</span></span>  
 [<span data-ttu-id="075b3-109">Основы управляемых потоков</span><span class="sxs-lookup"><span data-stu-id="075b3-109">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)  
 <span data-ttu-id="075b3-110">Обзор управляемых потоков и случаев использования нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="075b3-110">Provides an overview of managed threading and discusses when to use multiple threads.</span></span>  
  
 [<span data-ttu-id="075b3-111">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="075b3-111">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 <span data-ttu-id="075b3-112">Описание способов создания, запуска, приостановки, возобновления и отмены потоков.</span><span class="sxs-lookup"><span data-stu-id="075b3-112">Explains how to create, start, pause, resume, and abort threads.</span></span>  
  
 [<span data-ttu-id="075b3-113">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="075b3-113">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="075b3-114">Обсуждение уровней синхронизации, способов предотвращения взаимоблокировки и состояния гонки и других проблем, связанных с многопоточностью.</span><span class="sxs-lookup"><span data-stu-id="075b3-114">Discusses levels of synchronization, how to avoid deadlocks and race conditions, and other threading issues.</span></span>  
  
 [<span data-ttu-id="075b3-115">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="075b3-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 <span data-ttu-id="075b3-116">Описание управляемых классов, которые можно использовать для синхронизации действий потоков и данных объектов, доступных в разных потоках, а также обзор пула потоков.</span><span class="sxs-lookup"><span data-stu-id="075b3-116">Describes the managed classes you can use to synchronize the activities of threads and the data of objects accessed on different threads, and provides an overview of thread pool threads.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="075b3-117">Справочник</span><span class="sxs-lookup"><span data-stu-id="075b3-117">Reference</span></span>  
 <xref:System.Threading>  
 <span data-ttu-id="075b3-118">Содержит классы для использования и синхронизации управляемых потоков.</span><span class="sxs-lookup"><span data-stu-id="075b3-118">Contains classes for using and synchronizing managed threads.</span></span>  
  
 <xref:System.Collections.Concurrent>  
 <span data-ttu-id="075b3-119">Содержит классы коллекций, которые могут безопасно использоваться несколькими потоками.</span><span class="sxs-lookup"><span data-stu-id="075b3-119">Contains collection classes that are safe for use with multiple threads.</span></span>  
  
 <xref:System.Threading.Tasks>  
 <span data-ttu-id="075b3-120">Содержит классы для создания и планирования задач параллельной обработки.</span><span class="sxs-lookup"><span data-stu-id="075b3-120">Contains classes for creating and scheduling concurrent processing tasks.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="075b3-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="075b3-121">Related Sections</span></span>  
 [<span data-ttu-id="075b3-122">Домены приложений</span><span class="sxs-lookup"><span data-stu-id="075b3-122">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="075b3-123">Общие сведения о доменах приложений и их использовании в Common Language Infrastructure.</span><span class="sxs-lookup"><span data-stu-id="075b3-123">Provides an overview of application domains and their use by the Common Language Infrastructure.</span></span>  
  
 [<span data-ttu-id="075b3-124">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="075b3-124">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="075b3-125">Описывает преимущества и основные операции асинхронного ввода и вывода.</span><span class="sxs-lookup"><span data-stu-id="075b3-125">Describes the performance advantages and basic operation of asynchronous I/O.</span></span>  
  
 <span data-ttu-id="075b3-126">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))</span><span class="sxs-lookup"><span data-stu-id="075b3-126">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span>  
 <span data-ttu-id="075b3-127">Предоставляет общие рекомендации по асинхронному программированию в .NET.</span><span class="sxs-lookup"><span data-stu-id="075b3-127">Provides an overview of the recommended pattern for asynchronous programming in .NET.</span></span>  
  
 [<span data-ttu-id="075b3-128">Асинхронный вызов синхронных методов</span><span class="sxs-lookup"><span data-stu-id="075b3-128">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="075b3-129">Описание способов вызова методов в потоках пула потоков с помощью встроенных функций делегатов.</span><span class="sxs-lookup"><span data-stu-id="075b3-129">Explains how to call methods on thread pool threads using built-in features of delegates.</span></span>  
  
 [<span data-ttu-id="075b3-130">Параллельное программирование</span><span class="sxs-lookup"><span data-stu-id="075b3-130">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="075b3-131">Описание библиотек параллельного программирования, упрощающих использование нескольких потоков в приложениях.</span><span class="sxs-lookup"><span data-stu-id="075b3-131">Describes the parallel programming libraries, which simplify the use of multiple threads in applications.</span></span>  
  
 [<span data-ttu-id="075b3-132">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="075b3-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
 <span data-ttu-id="075b3-133">Описание системы для выполнения запросов в параллельном режиме, позволяющей воспользоваться преимуществами нескольких процессоров.</span><span class="sxs-lookup"><span data-stu-id="075b3-133">Describes a system for running queries in parallel, to take advantage of multiple processors.</span></span>
