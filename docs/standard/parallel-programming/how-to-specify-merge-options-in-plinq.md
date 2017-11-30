---
title: "Практическое руководство. Задание параметров слияния в PLINQ"
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
helpviewer_keywords: PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec601e8bbefd31650fb91c438b032942cfc93101
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="4fe64-102">Практическое руководство. Задание параметров слияния в PLINQ</span><span class="sxs-lookup"><span data-stu-id="4fe64-102">How to: Specify Merge Options in PLINQ</span></span>
<span data-ttu-id="4fe64-103">В этом примере показано, как указать параметры слияния, которые будут применяться ко всем последующим операторам в запросе PLINQ.</span><span class="sxs-lookup"><span data-stu-id="4fe64-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="4fe64-104">Нет необходимости явно задавать параметры слияния, но это может повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="4fe64-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="4fe64-105">Дополнительные сведения о параметрах слияния см. в разделе [параметров слияния в PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4fe64-105">For more information about merge options, see [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4fe64-106">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="4fe64-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="4fe64-107">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="4fe64-107">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fe64-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4fe64-108">Example</span></span>  
 <span data-ttu-id="4fe64-109">В следующем примере показано поведение параметров слияния в основном сценарии, который имеет неупорядоченный источник и применяет ресурсоемкую функцию к каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="4fe64-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="4fe64-110">В случаях, где <xref:System.Linq.ParallelMergeOptions.AutoBuffered> параметр приводит к нежелательной задержке перед получением первого элемента, попробуйте <xref:System.Linq.ParallelMergeOptions.NotBuffered> параметр, чтобы получить результирующие элементы быстро и гладко.</span><span class="sxs-lookup"><span data-stu-id="4fe64-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe64-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4fe64-111">See Also</span></span>  
 <xref:System.Linq.ParallelMergeOptions>  
 [<span data-ttu-id="4fe64-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="4fe64-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
