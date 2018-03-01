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
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e83505a36252457d286bc7fbc6bbe442732229a4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="spinlock"></a><span data-ttu-id="756f6-102">SpinLock</span><span class="sxs-lookup"><span data-stu-id="756f6-102">SpinLock</span></span>
<span data-ttu-id="756f6-103">Структура <xref:System.Threading.SpinLock> — это примитив низкоуровневой синхронизации со взаимоисключающей блокировкой, которая выполняет цикл ожидания, пока не получит блокировку.</span><span class="sxs-lookup"><span data-stu-id="756f6-103">The <xref:System.Threading.SpinLock> structure is a low-level, mutual-exclusion synchronization primitive that spins while it waits to acquire a lock.</span></span> <span data-ttu-id="756f6-104">На многоядерных компьютерах, если предполагается короткое время ожидания и минимальный риск состязаний, <xref:System.Threading.SpinLock> может выполняться быстрее, чем другие виды блокировок.</span><span class="sxs-lookup"><span data-stu-id="756f6-104">On multicore computers, when wait times are expected to be short and when contention is minimal, <xref:System.Threading.SpinLock> can perform better than other kinds of locks.</span></span> <span data-ttu-id="756f6-105">Но мы рекомендуем использовать <xref:System.Threading.SpinLock> только в том случае, если в ходе профилирования подтверждается существенное ухудшение производительности при работе с методом <xref:System.Threading.Monitor?displayProperty=nameWithType> и методами <xref:System.Threading.Interlocked>.</span><span class="sxs-lookup"><span data-stu-id="756f6-105">However, we recommend that you use <xref:System.Threading.SpinLock> only when you determine by profiling that the <xref:System.Threading.Monitor?displayProperty=nameWithType> method or the <xref:System.Threading.Interlocked> methods are significantly slowing the performance of your program.</span></span>  
  
 <span data-ttu-id="756f6-106"><xref:System.Threading.SpinLock> может освободить квант процессорного времени для потока, даже не создав блокировку.</span><span class="sxs-lookup"><span data-stu-id="756f6-106"><xref:System.Threading.SpinLock> may yield the time slice of the thread even if it has not yet acquired the lock.</span></span> <span data-ttu-id="756f6-107">Такое поведение позволяет избежать инверсии приоритетов потока, а также не мешать работе сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="756f6-107">It does this to avoid thread-priority inversion, and to enable the garbage collector to make progress.</span></span> <span data-ttu-id="756f6-108">При работе с <xref:System.Threading.SpinLock> важно гарантировать, чтобы ни один поток не устанавливал блокировку дольше, чем на очень короткий промежуток времени, и чтобы ни один поток не мог заблокироваться в режиме удержания блокировки.</span><span class="sxs-lookup"><span data-stu-id="756f6-108">When you use a <xref:System.Threading.SpinLock>, ensure that no thread can hold the lock for more than a very brief time span, and that no thread can block while it holds the lock.</span></span>  
  
 <span data-ttu-id="756f6-109">Поскольку SpinLock является типом значения, его необходимо явным образом передавать по ссылке, если две копии значения должны указывать на одну и ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="756f6-109">Because SpinLock is a value type, you must explicitly pass it by reference if you intend the two copies to refer to the same lock.</span></span>  
  
 <span data-ttu-id="756f6-110">Дополнительные сведения об использовании этого типа см. в статье о структуре <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="756f6-110">For more information about how to use this type, see <xref:System.Threading.SpinLock?displayProperty=nameWithType>.</span></span> <span data-ttu-id="756f6-111">Некоторые примеры есть в статье [Практическое руководство. SpinLock и низкоуровневая синхронизация](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="756f6-111">For an example, see [How to: Use SpinLock for Low-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md).</span></span>  
  
 <span data-ttu-id="756f6-112"><xref:System.Threading.SpinLock> поддерживает режим *отслеживания*-*потоков*, удобный на этапе разработки для выявления потока, который удерживает блокировку в конкретный момент времени.</span><span class="sxs-lookup"><span data-stu-id="756f6-112"><xref:System.Threading.SpinLock> supports a *thread*-*tracking* mode that you can use during the development phase to help track the thread that is holding the lock at a specific time.</span></span> <span data-ttu-id="756f6-113">Режим отслеживания потоков очень полезен для отладки, но мы рекомендуем отключать его в рабочей версии программы, чтобы не снижать производительность.</span><span class="sxs-lookup"><span data-stu-id="756f6-113">Thread-tracking mode is very useful for debugging, but we recommend that you turn it off in the release version of your program because it may slow performance.</span></span> <span data-ttu-id="756f6-114">Дополнительные сведения см. в статье [Практическое руководство. Включение режима отслеживания потоков в SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span><span class="sxs-lookup"><span data-stu-id="756f6-114">For more information, see [How to: Enable Thread-Tracking Mode in SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756f6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="756f6-115">See Also</span></span>  
 [<span data-ttu-id="756f6-116">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="756f6-116">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
