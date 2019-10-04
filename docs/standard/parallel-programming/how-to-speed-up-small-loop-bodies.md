---
title: Практическое руководство. Повышение скорости выполнения небольших тел циклов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fde68d0a938ed04380bf0e99cc0c544793571d77
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965583"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="9e21a-102">Практическое руководство. Повышение скорости выполнения небольших тел циклов</span><span class="sxs-lookup"><span data-stu-id="9e21a-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="9e21a-103">Когда цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> имеет небольшое тело, он может выполняться значительно медленнее, чем эквивалентный последовательный цикл, такой как цикл [for](../../csharp/language-reference/keywords/for.md) в C# и цикл [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9e21a-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="9e21a-104">Снижение производительности происходит вследствие нагрузки, связанной с секционированием данных и стоимостью вызова делегата в каждой итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="9e21a-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="9e21a-105">Для разрешения таких сценариев класс <xref:System.Collections.Concurrent.Partitioner> предоставляет метод <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, который позволяет выполнять последовательный цикл для тела делегата, чтобы делегат вызывался только один раз для каждой секции, а не по разу в каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="9e21a-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="9e21a-106">Дополнительные сведения см. в разделе [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="9e21a-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e21a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9e21a-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="9e21a-108">Подход, продемонстрированный в данном примере, полезно использовать в тех случаях, когда цикл выполняет минимальный объем работ.</span><span class="sxs-lookup"><span data-stu-id="9e21a-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="9e21a-109">Когда работа начнет потреблять больше вычислительных ресурсов, возможно, вы получите такую же или более высокую производительность с помощью цикла <xref:System.Threading.Tasks.Parallel.For%2A> или <xref:System.Threading.Tasks.Parallel.ForEach%2A> с разделителем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9e21a-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e21a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="9e21a-110">See also</span></span>

- [<span data-ttu-id="9e21a-111">Параллелизм данных</span><span class="sxs-lookup"><span data-stu-id="9e21a-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="9e21a-112">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="9e21a-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- <span data-ttu-id="9e21a-113">[Iterators (C#)](../../csharp/programming-guide/concepts/iterators.md) (Итераторы (C#))</span><span class="sxs-lookup"><span data-stu-id="9e21a-113">[Iterators (C#)](../../csharp/programming-guide/concepts/iterators.md)</span></span>
- <span data-ttu-id="9e21a-114">[Iterators (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md) (Итераторы (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9e21a-114">[Iterators (Visual Basic)](../../visual-basic/programming-guide/concepts/iterators.md)</span></span>
- [<span data-ttu-id="9e21a-115">Лямбда-выражения в PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="9e21a-115">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
