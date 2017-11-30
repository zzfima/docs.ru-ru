---
title: "Практическое руководство. SpinLock и низкоуровневая синхронизация"
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="476aa-102">Практическое руководство. SpinLock и низкоуровневая синхронизация</span><span class="sxs-lookup"><span data-stu-id="476aa-102">How to: Use SpinLock for Low-Level Synchronization</span></span>
<span data-ttu-id="476aa-103">В следующем примере демонстрируется использование <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="476aa-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="476aa-104">Пример</span><span class="sxs-lookup"><span data-stu-id="476aa-104">Example</span></span>  
 <span data-ttu-id="476aa-105">В этом примере критический раздел выполняет минимальный объем работы, который вполне подходит для <xref:System.Threading.SpinLock>.</span><span class="sxs-lookup"><span data-stu-id="476aa-105">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="476aa-106">Увеличивая работы небольшую повышает производительность <xref:System.Threading.SpinLock> по сравнению со стандартной блокировкой.</span><span class="sxs-lookup"><span data-stu-id="476aa-106">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="476aa-107">При этом в определенный момент SpinLock может оказаться дороже стандартной блокировки.</span><span class="sxs-lookup"><span data-stu-id="476aa-107">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="476aa-108">Чтобы увидеть, какой тип блокировки обеспечивает наибольшую производительность в вашей программе, воспользуйтесь функцией профилирования параллелизма.</span><span class="sxs-lookup"><span data-stu-id="476aa-108">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="476aa-109">Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="476aa-109">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="476aa-110"><xref:System.Threading.SpinLock>может оказаться полезным при блокировку на ресурс общего доступа не будет сохраняться очень много.</span><span class="sxs-lookup"><span data-stu-id="476aa-110"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="476aa-111">В подобных случаях на многоядерных компьютерах полезно запустить заблокированный поток на несколько циклов, пока блокировка не будет снята.</span><span class="sxs-lookup"><span data-stu-id="476aa-111">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="476aa-112">За счет цикличности поток не блокируется, а значит ресурсы процессора активно используются.</span><span class="sxs-lookup"><span data-stu-id="476aa-112">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="476aa-113"><xref:System.Threading.SpinLock>остановит цикл при определенных условиях, чтобы избежать неэффективной работы логических процессоров или инверсии приоритетов в системах с технологией Hyper-Threading.</span><span class="sxs-lookup"><span data-stu-id="476aa-113"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="476aa-114">В этом примере используется <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> класс, для которого необходима синхронизация пользователей для многопоточного доступа.</span><span class="sxs-lookup"><span data-stu-id="476aa-114">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="476aa-115">В приложениях, предназначенных для .NET Framework версии 4, другой вариант — использовать <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, который не требует никаких блокировок пользователя.</span><span class="sxs-lookup"><span data-stu-id="476aa-115">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="476aa-116">Обратите внимание на использование `false` (`False` в Visual Basic) в вызове <xref:System.Threading.SpinLock.Exit%2A>.</span><span class="sxs-lookup"><span data-stu-id="476aa-116">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A>.</span></span> <span data-ttu-id="476aa-117">Это обеспечивает оптимальную производительность.</span><span class="sxs-lookup"><span data-stu-id="476aa-117">This provides the best performance.</span></span> <span data-ttu-id="476aa-118">Укажите архитектуры `true` (`True`)on IA64, чтобы воспользоваться барьером памяти, который очищает буферы записи, обеспечивая таким образом блокировку для завершения работы других потоков.</span><span class="sxs-lookup"><span data-stu-id="476aa-118">Specify `true` (`True`)on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="476aa-119">См. также</span><span class="sxs-lookup"><span data-stu-id="476aa-119">See Also</span></span>  
 [<span data-ttu-id="476aa-120">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="476aa-120">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
