---
title: "Метод Thread.Suspend, сборка мусора и безопасные точки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a><span data-ttu-id="aaf38-102">Метод Thread.Suspend, сборка мусора и безопасные точки</span><span class="sxs-lookup"><span data-stu-id="aaf38-102">Thread.Suspend, Garbage Collection, and Safe Points</span></span>
<span data-ttu-id="aaf38-103">При вызове <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> в потоке, система сообщает о был запрошен и позволяет потоку выполняться, пока он достигнет безопасной точки поступившем приостановку потока.</span><span class="sxs-lookup"><span data-stu-id="aaf38-103">When you call <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> on a thread, the system notes that a thread suspension has been requested and allows the thread to execute until it has reached a safe point before actually suspending the thread.</span></span> <span data-ttu-id="aaf38-104">Безопасные точки для потока является точкой, в ходе выполнения, на какие сборки мусора могут выполняться коллекции.</span><span class="sxs-lookup"><span data-stu-id="aaf38-104">A safe point for a thread is a point in its execution at which garbage collection can be performed.</span></span>  
  
 <span data-ttu-id="aaf38-105">После достижения безопасной точки среды выполнения гарантирует, что поток не будет выполнять продолжить работу в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="aaf38-105">Once a safe point is reached, the runtime guarantees that the suspended thread will not make any further progress in managed code.</span></span> <span data-ttu-id="aaf38-106">Поток выполняется вне управляемого кода всегда безопасно для сборки мусора, и его выполнение продолжается, пока он попытается возобновить выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="aaf38-106">A thread executing outside managed code is always safe for garbage collection, and its execution continues until it attempts to resume execution of managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aaf38-107">Чтобы выполнить сборку мусора, среде выполнения необходимо приостановить все потоки, за исключением потока, отвечающего коллекции.</span><span class="sxs-lookup"><span data-stu-id="aaf38-107">In order to perform a garbage collection, the runtime must suspend all the threads except the thread performing the collection.</span></span> <span data-ttu-id="aaf38-108">Каждый поток должен достичь безопасной точки, прежде чем можно будет приостановить.</span><span class="sxs-lookup"><span data-stu-id="aaf38-108">Each thread must be brought to a safe point before it can be suspended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf38-109">См. также</span><span class="sxs-lookup"><span data-stu-id="aaf38-109">See Also</span></span>  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [<span data-ttu-id="aaf38-110">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="aaf38-110">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="aaf38-111">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="aaf38-111">Automatic Memory Management</span></span>](../../../docs/standard/automatic-memory-management.md)
