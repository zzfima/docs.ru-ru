---
title: Метод Thread.Suspend, сборка мусора и безопасные точки
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3af01167fe97b701bdb0c7bc37af02d8e8a77c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004183"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="86364-102">Метод Thread.Suspend, сборка мусора и безопасные точки</span><span class="sxs-lookup"><span data-stu-id="86364-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="86364-103">Когда вы вызываете для потока <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>, система фиксирует запрос на приостановку потока и позволяет ему продолжить работу до безопасной точки, а лишь затем выполняет приостановку.</span><span class="sxs-lookup"><span data-stu-id="86364-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="86364-104">Безопасной точкой для потока считается такой этап выполнения, в котором можно безопасно выполнять сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="86364-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="86364-105">После достижения безопасной точки среда выполнения гарантирует, что поток не выполняет никаких действий в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="86364-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="86364-106">В потоке, выполняемом вне управляемого кода, всегда можно безопасно выполнить сборку мусора, поэтому его выполнение продолжается, пока он попытается возобновить выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="86364-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86364-107">Чтобы выполнить сборку мусора, среда выполнения приостанавливает все потоки, за исключением самого потока сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="86364-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="86364-108">Каждый поток должен достичь безопасной точки, чтобы его можно было приостановить.</span><span class="sxs-lookup"><span data-stu-id="86364-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86364-109">См. также</span><span class="sxs-lookup"><span data-stu-id="86364-109">See also</span></span>

- <xref:System.Threading.Thread>  
- <xref:System.GC>  
- [<span data-ttu-id="86364-110">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="86364-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="86364-111">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="86364-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
