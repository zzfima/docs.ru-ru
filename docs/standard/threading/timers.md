---
title: "таймеры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a><span data-ttu-id="4e6d1-102">таймеры</span><span class="sxs-lookup"><span data-stu-id="4e6d1-102">Timers</span></span>
<span data-ttu-id="4e6d1-103">Таймеры являются простые объекты, которые позволяют указать делегат, вызываемый в указанное время.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="4e6d1-104">Поток в пуле потоков выполняет операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="4e6d1-105">С помощью <xref:System.Threading.Timer?displayProperty=nameWithType> класса выполняется просто.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="4e6d1-106">Вы создаете **таймера**, передав <xref:System.Threading.TimerCallback> делегат для метода обратного вызова, объект, представляющий состояние, которое будет передано обратного вызова, raise начальное время и время, представляющий время обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="4e6d1-107">Чтобы отменить ожидающие таймера, вызовите **Timer.Dispose** функции.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e6d1-108">Существует два других класса таймера.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-108">There are two other timer classes.</span></span> <span data-ttu-id="4e6d1-109"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType> Элемент управления, который используется в конструкторах visual и предназначен для использования в контекстах пользовательского интерфейса; он создает события в потоке пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="4e6d1-110"><xref:System.Timers.Timer?displayProperty=nameWithType> Класс является производным от <xref:System.ComponentModel.Component>, поэтому он может использоваться с визуальными конструкторами; он также создает события, но делает это в <xref:System.Threading.ThreadPool> потока.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="4e6d1-111"><xref:System.Threading.Timer?displayProperty=nameWithType> Класс выполняет обратные вызовы <xref:System.Threading.ThreadPool> потоков и вообще не использовать модель событий.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="4e6d1-112">Он также предоставляет объект состояния методу обратного вызова, который другие таймеры этого не делают.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="4e6d1-113">Он является очень облегченным.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="4e6d1-114">В следующем примере кода запускается таймер, который начинает работу после одной секунды (1000 миллисекунд) и отсчитывает каждую секунду до нажатия клавиши **ввод** ключа.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="4e6d1-115">Переменная, содержащая ссылку на таймер является полем уровня класса, чтобы убедиться, что таймер не подвергаются сборке мусора пока она продолжает работать.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="4e6d1-116">Дополнительные сведения об агрессивной сборке мусора см. в разделе <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e6d1-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4e6d1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4e6d1-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="4e6d1-118">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="4e6d1-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
