---
title: "Практическое руководство. Повышение скорости выполнения небольших тел циклов"
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
helpviewer_keywords: parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d38d8beedf342720d4dc68026297edb457f5ed35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="46de8-102">Практическое руководство. Повышение скорости выполнения небольших тел циклов</span><span class="sxs-lookup"><span data-stu-id="46de8-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="46de8-103">Когда <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> цикл имеет небольшое тело, он может выполняться медленнее, чем эквивалентный последовательный цикл, таких как [для](~/docs/csharp/language-reference/keywords/for.md) в C# и [для](http://msdn.microsoft.com/en-us/c470a263-9b49-4308-8fd6-8592b84a7980) цикл в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46de8-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](~/docs/csharp/language-reference/keywords/for.md) loop in C# and the [For](http://msdn.microsoft.com/en-us/c470a263-9b49-4308-8fd6-8592b84a7980) loop in Visual Basic.</span></span> <span data-ttu-id="46de8-104">Снижение производительности происходит вследствие нагрузки, связанной с секционированием данных и стоимостью вызова делегата в каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="46de8-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="46de8-105">Для разрешения таких сценариев класс <xref:System.Collections.Concurrent.Partitioner> предоставляет метод <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, который позволяет выполнять последовательный цикл для тела делегата, чтобы делегат вызывался только один раз для каждой секции, а не по разу в каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="46de8-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="46de8-106">Дополнительные сведения см. в разделе [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="46de8-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46de8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="46de8-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="46de8-108">Подход, продемонстрированный в данном примере, полезно использовать в тех случаях, когда цикл выполняет минимальный объем работ.</span><span class="sxs-lookup"><span data-stu-id="46de8-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="46de8-109">Когда работа начнет потреблять больше вычислительных ресурсов, возможно, вы получите такую же или более высокую производительность с помощью цикла <xref:System.Threading.Tasks.Parallel.For%2A> или <xref:System.Threading.Tasks.Parallel.ForEach%2A> с разделителем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46de8-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46de8-110">См. также</span><span class="sxs-lookup"><span data-stu-id="46de8-110">See Also</span></span>  
 [<span data-ttu-id="46de8-111">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="46de8-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [<span data-ttu-id="46de8-112">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="46de8-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [<span data-ttu-id="46de8-113">Итераторы</span><span class="sxs-lookup"><span data-stu-id="46de8-113">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [<span data-ttu-id="46de8-114">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="46de8-114">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
