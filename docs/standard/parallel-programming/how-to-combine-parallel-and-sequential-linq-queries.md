---
title: "Практическое руководство. Объединение параллельных и последовательных запросов LINQ"
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
helpviewer_keywords: parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4da91ff535059b181baa637164a854cd75d06334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a><span data-ttu-id="017fd-102">Практическое руководство. Объединение параллельных и последовательных запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="017fd-102">How to: Combine Parallel and Sequential LINQ Queries</span></span>
<span data-ttu-id="017fd-103">В этом примере показано, как использовать <xref:System.Linq.ParallelEnumerable.AsSequential%2A> метод для указания PLINQ последовательно обрабатывать все последующие операторы в запросе.</span><span class="sxs-lookup"><span data-stu-id="017fd-103">This example shows how to use the <xref:System.Linq.ParallelEnumerable.AsSequential%2A> method to instruct PLINQ to process all subsequent operators in the query sequentially.</span></span> <span data-ttu-id="017fd-104">Хотя обычно медленнее, чем параллельный последовательная обработка, иногда это необходимо для получения правильных результатов.</span><span class="sxs-lookup"><span data-stu-id="017fd-104">Although sequential processing is generally slower than parallel, sometimes it is necessary to produce correct results.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="017fd-105">Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.</span><span class="sxs-lookup"><span data-stu-id="017fd-105">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="017fd-106">Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="017fd-106">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="017fd-107">Пример</span><span class="sxs-lookup"><span data-stu-id="017fd-107">Example</span></span>  
 <span data-ttu-id="017fd-108">В следующем примере показано один сценарий, в котором <xref:System.Linq.ParallelEnumerable.AsSequential%2A> является обязательным, а именно для сохранения порядка, установленного в предыдущем предложении запроса.</span><span class="sxs-lookup"><span data-stu-id="017fd-108">The following example shows one scenario in which <xref:System.Linq.ParallelEnumerable.AsSequential%2A> is required, namely to preserve the ordering that was established in a previous clause of the query.</span></span>  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="017fd-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="017fd-109">Compiling the Code</span></span>  
 <span data-ttu-id="017fd-110">Чтобы скомпилировать и запустить этот код, вставьте его в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) проекта, добавьте строку, вызовите метод из `Main`, и нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="017fd-110">To compile and run this code, paste it into the [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) project, add a line to call the method from `Main`, and press F5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017fd-111">См. также</span><span class="sxs-lookup"><span data-stu-id="017fd-111">See Also</span></span>  
 [<span data-ttu-id="017fd-112">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="017fd-112">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
