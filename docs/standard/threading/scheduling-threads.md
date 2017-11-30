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
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a><span data-ttu-id="b1802-102">Расписание потоков</span><span class="sxs-lookup"><span data-stu-id="b1802-102">Scheduling Threads</span></span>
<span data-ttu-id="b1802-103">Каждый поток имеет приоритет потока, назначенного ей.</span><span class="sxs-lookup"><span data-stu-id="b1802-103">Every thread has a thread priority assigned to it.</span></span> <span data-ttu-id="b1802-104">Потоки, созданные в общеязыковая среда выполнения, изначально присваивается приоритет **ThreadPriority.Normal**.</span><span class="sxs-lookup"><span data-stu-id="b1802-104">Threads created within the common language runtime are initially assigned the priority of **ThreadPriority.Normal**.</span></span> <span data-ttu-id="b1802-105">Потоки, созданные за пределами среды сохраняется приоритет, который они имели до входа управляемой среды.</span><span class="sxs-lookup"><span data-stu-id="b1802-105">Threads created outside the runtime retain the priority they had before they entered the managed environment.</span></span> <span data-ttu-id="b1802-106">Можно получить или задать приоритет для потока с **Thread.Priority** свойство.</span><span class="sxs-lookup"><span data-stu-id="b1802-106">You can get or set the priority of any thread with the **Thread.Priority** property.</span></span>  
  
 <span data-ttu-id="b1802-107">Потоки планируются для выполнения на основе их приоритета.</span><span class="sxs-lookup"><span data-stu-id="b1802-107">Threads are scheduled for execution based on their priority.</span></span> <span data-ttu-id="b1802-108">Несмотря на то, что потоки, выполняемые в среде выполнения, все потоки выделяет время процессора в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b1802-108">Even though threads are executing within the runtime, all threads are assigned processor time slices by the operating system.</span></span> <span data-ttu-id="b1802-109">Сведения о планировании алгоритм, используемый для определения порядка, в котором выполняются потоки зависит от каждой операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b1802-109">The details of the scheduling algorithm used to determine the order in which threads are executed varies with each operating system.</span></span> <span data-ttu-id="b1802-110">В некоторых операционных системах поток с наивысшим приоритетом (из этих потоков, которые могут быть выполнены) всегда планируется для первого запуска.</span><span class="sxs-lookup"><span data-stu-id="b1802-110">Under some operating systems, the thread with the highest priority (of those threads that can be executed) is always scheduled to run first.</span></span> <span data-ttu-id="b1802-111">Если несколько потоков с одинаковым приоритетом, все доступные, планировщик циклически проходит по потокам с данным приоритетом и назначает каждому из потоков срез фиксированное время, в которой выполняется.</span><span class="sxs-lookup"><span data-stu-id="b1802-111">If multiple threads with the same priority are all available, the scheduler cycles through the threads at that priority, giving each thread a fixed time slice in which to execute.</span></span> <span data-ttu-id="b1802-112">При условии, что поток с более высоким приоритетом будут доступны для выполнения, ниже приоритет потоков не будут.</span><span class="sxs-lookup"><span data-stu-id="b1802-112">As long as a thread with a higher priority is available to run, lower priority threads do not get to execute.</span></span> <span data-ttu-id="b1802-113">Если больше нет потоков с заданным приоритетом, планировщик переходит к более низким приоритетом и планирует потоков с приоритетом, что для выполнения.</span><span class="sxs-lookup"><span data-stu-id="b1802-113">When there are no more runnable threads at a given priority, the scheduler moves to the next lower priority and schedules the threads at that priority for execution.</span></span> <span data-ttu-id="b1802-114">Если поток с высоким приоритетом становится работоспособным, он, ниже приоритет потока прерывается и может выполняться еще раз поток более высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="b1802-114">If a higher priority thread becomes runnable, the lower priority thread is preempted and the higher priority thread is allowed to execute once again.</span></span> <span data-ttu-id="b1802-115">Все, операционной системы можно также динамически настраивать приоритеты потоков пользовательского интерфейса приложения при перемещении между переднего плана и фона.</span><span class="sxs-lookup"><span data-stu-id="b1802-115">On top of all that, the operating system can also adjust thread priorities dynamically as an application's user interface is moved between foreground and background.</span></span> <span data-ttu-id="b1802-116">Другие операционные системы можно использовать другой алгоритм планирования.</span><span class="sxs-lookup"><span data-stu-id="b1802-116">Other operating systems might choose to use a different scheduling algorithm.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1802-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b1802-117">See Also</span></span>  
 [<span data-ttu-id="b1802-118">Использование потоков и работа с потоками</span><span class="sxs-lookup"><span data-stu-id="b1802-118">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)  
 [<span data-ttu-id="b1802-119">Управляемые и неуправляемые потоки в Windows</span><span class="sxs-lookup"><span data-stu-id="b1802-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
