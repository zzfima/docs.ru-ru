---
title: "Практическое руководство. Реализация динамических разделов"
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
helpviewer_keywords: tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1e5dc93997918e0f7da29fa1f94c434a556f19f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="11245-102">Практическое руководство. Реализация динамических разделов</span><span class="sxs-lookup"><span data-stu-id="11245-102">How to: Implement Dynamic Partitions</span></span>
<span data-ttu-id="11245-103">В следующем примере показано, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , реализует динамическое секционирование и может использоваться посредством определенных перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и PLINQ.</span><span class="sxs-lookup"><span data-stu-id="11245-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11245-104">Пример</span><span class="sxs-lookup"><span data-stu-id="11245-104">Example</span></span>  
 <span data-ttu-id="11245-105">Каждый раз раздел вызывает <xref:System.Collections.IEnumerator.MoveNext%2A> в перечислителе, перечислитель предоставляет раздел с одним элементом списка.</span><span class="sxs-lookup"><span data-stu-id="11245-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="11245-106">В случае с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A>, секция является <xref:System.Threading.Tasks.Task> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="11245-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="11245-107">Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.</span><span class="sxs-lookup"><span data-stu-id="11245-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 <span data-ttu-id="11245-108">Это пример разделения по блокам, где каждый блок состоит из одного элемента.</span><span class="sxs-lookup"><span data-stu-id="11245-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="11245-109">Предоставляя несколько элементов одновременно, можно уменьшить конфликты через блокировку и теоретически увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="11245-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="11245-110">Однако в определенный момент большими частями может потребоваться дополнительная логика балансировки нагрузки для поддержания нагрузки всех потоков до завершения всех действий.</span><span class="sxs-lookup"><span data-stu-id="11245-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11245-111">См. также</span><span class="sxs-lookup"><span data-stu-id="11245-111">See Also</span></span>  
 [<span data-ttu-id="11245-112">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="11245-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="11245-113">Практическое руководство. Реализация разделителя для статического секционирования</span><span class="sxs-lookup"><span data-stu-id="11245-113">How to: Implement a Partitioner for Static Partitioning</span></span>](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
