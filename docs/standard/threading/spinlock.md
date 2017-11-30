---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a><span data-ttu-id="42043-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="42043-102">SpinLock</span></span>
<span data-ttu-id="42043-103"><xref:System.Threading.SpinLock> Структуры — это низкоуровневые взаимного исключения примитив синхронизации, который выполняет цикл в ожидании получения блокировки.</span><span class="sxs-lookup"><span data-stu-id="42043-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="42043-104">На многоядерных компьютерах, если предполагается, что время ожидания короткий и будет минимально и <xref:System.Threading.SpinLock> можно выполнить быстрее, чем другие виды блокировок.</span><span class="sxs-lookup"><span data-stu-id="42043-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="42043-105">Тем не менее, мы рекомендуем использовать <xref:System.Threading.SpinLock> только при определении профилирования показывают, что <xref:System.Threading.Monitor?displayProperty=nameWithType> метода или <xref:System.Threading.Interlocked> методы значительно снижают производительность программы.</span><span class="sxs-lookup"><span data-stu-id="42043-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="42043-106"><xref:System.Threading.SpinLock>может привести временной срез потока, даже если он ещё не получила блокировку.</span><span class="sxs-lookup"><span data-stu-id="42043-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="42043-107">Это делается во избежание инверсии приоритет потока, а также поддерживать сборщик мусора прогресса.</span><span class="sxs-lookup"><span data-stu-id="42043-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="42043-108">При использовании <xref:System.Threading.SpinLock>, убедитесь, что ни один поток не может быть установлена блокировка более короткая временной интервал, и что ни один поток можно заблокировать во время удержания блокировки.</span><span class="sxs-lookup"><span data-stu-id="42043-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="42043-109">Поскольку SpinLock является типом значения, необходимо явным образом передать его по ссылке, если планируется две копии для ссылки на ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="42043-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="42043-110">Дополнительные сведения об использовании этого типа см. в разделе <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="42043-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="42043-111">Пример см. в разделе [как: SpinLock используется для синхронизации нижнего уровня](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="42043-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="42043-112"><xref:System.Threading.SpinLock>поддерживает *поток*-*отслеживания* режим, который можно использовать на этапе разработки для отслеживания потока, который удерживает блокировку в определенное время.</span><span class="sxs-lookup"><span data-stu-id="42043-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="42043-113">Режим отслеживания потоков очень полезен для отладки, но мы рекомендуем отключить его в окончательной версии программы, так как может привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="42043-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="42043-114">Дополнительные сведения см. в разделе [как: режим включить поток отслеживания в SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="42043-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42043-115">См. также</span><span class="sxs-lookup"><span data-stu-id="42043-115">See Also</span></span>  
 [<span data-ttu-id="42043-116">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="42043-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
