---
title: "Расписание потоков"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6bb715c11cc0d9b07e4ea8805ace7680ca92097c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="scheduling-threads"></a><span data-ttu-id="ab991-102">Расписание потоков</span><span class="sxs-lookup"><span data-stu-id="ab991-102">Scheduling Threads</span></span>
<span data-ttu-id="ab991-103">Каждому потоку назначается определенный приоритет.</span><span class="sxs-lookup"><span data-stu-id="ab991-103">Every thread has a thread priority assigned to it.</span></span> <span data-ttu-id="ab991-104">Потокам, созданным в общеязыковой среде выполнения, изначально назначается приоритет **ThreadPriority.Normal**.</span><span class="sxs-lookup"><span data-stu-id="ab991-104">Threads created within the common language runtime are initially assigned the priority of **ThreadPriority.Normal**.</span></span> <span data-ttu-id="ab991-105">Потоки, созданные за пределами среды выполнения, сохраняют приоритет, который они имели до входа в управляемую среду.</span><span class="sxs-lookup"><span data-stu-id="ab991-105">Threads created outside the runtime retain the priority they had before they entered the managed environment.</span></span> <span data-ttu-id="ab991-106">Вы можете получить или задать приоритет для любого потока, используя свойство **Thread.Priority**.</span><span class="sxs-lookup"><span data-stu-id="ab991-106">You can get or set the priority of any thread with the **Thread.Priority** property.</span></span>  
  
 <span data-ttu-id="ab991-107">Потоки назначаются на выполнение с учетом их приоритетов.</span><span class="sxs-lookup"><span data-stu-id="ab991-107">Threads are scheduled for execution based on their priority.</span></span> <span data-ttu-id="ab991-108">Несмотря на то, что потоки выполняются в среде выполнения, процессорное время им выделяет операционная система.</span><span class="sxs-lookup"><span data-stu-id="ab991-108">Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.</span></span> <span data-ttu-id="ab991-109">Конкретный алгоритм планирования, который определяет порядок выполнения потоков, будет разным у каждой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ab991-109">The details of the scheduling algorithm used to determine the order in which threads are executed varies with each operating system.</span></span> <span data-ttu-id="ab991-110">В некоторых операционных системах первым всегда выполняется поток с наивысшим приоритетом (из числа тех потоков, которые готовы к выполнению).</span><span class="sxs-lookup"><span data-stu-id="ab991-110">Under some operating systems, the thread with the highest priority (of those threads that can be executed) is always scheduled to run first.</span></span> <span data-ttu-id="ab991-111">Если доступны несколько потоков с одинаковым приоритетом, планировщик поочередно запускает все потоки с этим приоритетом, выделяя каждому фиксированное время для выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab991-111">If multiple threads with the same priority are all available, the scheduler cycles through the threads at that priority, giving each thread a fixed time slice in which to execute.</span></span> <span data-ttu-id="ab991-112">Пока есть хоть один доступный для выполнения поток с более высоким приоритетом, ни один из потоков с более низким приоритетом не запускается.</span><span class="sxs-lookup"><span data-stu-id="ab991-112">As long as a thread with a higher priority is available to run, lower priority threads do not get to execute.</span></span> <span data-ttu-id="ab991-113">Когда не останется ни одного готового потока с этим приоритетом, планировщик назначает для выполнения потоки со следующим, более низким, приоритетом.</span><span class="sxs-lookup"><span data-stu-id="ab991-113">When there are no more runnable threads at a given priority, the scheduler moves to the next lower priority and schedules the threads at that priority for execution.</span></span> <span data-ttu-id="ab991-114">Если в любой момент будет готов поток с более высоким приоритетом, поток с низким приоритетом сразу же прерывается и вместо него снова запускается поток с более высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="ab991-114">If a higher priority thread becomes runnable, the lower priority thread is preempted and the higher priority thread is allowed to execute once again.</span></span> <span data-ttu-id="ab991-115">Кроме того, операционная система может динамически изменять приоритеты потоков при перемещении пользовательского интерфейса приложения на передний план или в фоновый режим.</span><span class="sxs-lookup"><span data-stu-id="ab991-115">On top of all that, the operating system can also adjust thread priorities dynamically as an application's user interface is moved between foreground and background.</span></span> <span data-ttu-id="ab991-116">Другие операционные системы могут использовать другой алгоритм планирования.</span><span class="sxs-lookup"><span data-stu-id="ab991-116">Other operating systems might choose to use a different scheduling algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab991-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ab991-117">See Also</span></span>  
 [<span data-ttu-id="ab991-118">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="ab991-118">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="ab991-119">Управляемые и неуправляемые потоки в Windows</span><span class="sxs-lookup"><span data-stu-id="ab991-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
