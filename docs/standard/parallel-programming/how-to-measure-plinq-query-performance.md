---
title: Практическое руководство. Измерение производительности запросов PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 91b6165be2f4f464626fb25f7152de68de9d86e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124998"
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="252a0-102">Практическое руководство. Измерение производительности запросов PLINQ</span><span class="sxs-lookup"><span data-stu-id="252a0-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="252a0-103">В этом примере показано, как использовать класс <xref:System.Diagnostics.Stopwatch> для измерения времени, необходимого для выполнения запроса PLINQ.</span><span class="sxs-lookup"><span data-stu-id="252a0-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="252a0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="252a0-104">Example</span></span>  
 <span data-ttu-id="252a0-105">В этом примере для измерения времени, необходимого для выполнения запроса, используется пустой цикл `foreach` (`For Each` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="252a0-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="252a0-106">На практике цикл обычно содержит дополнительные этапы обработки, увеличивающие общее время выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="252a0-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="252a0-107">Обратите внимание, что секундомер запускается только перед началом цикла, так как именно в это время начинается выполнение запроса.</span><span class="sxs-lookup"><span data-stu-id="252a0-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="252a0-108">Если вам требуется более точное измерение, вместо `ElapsedTicks` можно использовать свойство `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="252a0-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="252a0-109">Общее время выполнения служит полезным показателем в экспериментах с реализациями запроса, но не всегда раскрывает общую картину.</span><span class="sxs-lookup"><span data-stu-id="252a0-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="252a0-110">Более глубокое и полное представление о взаимодействии потоков запроса друг с другом и с другими запущенными процессами можно получить, используя визуализатор параллелизма.</span><span class="sxs-lookup"><span data-stu-id="252a0-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="252a0-111">Дополнительные сведения см. в разделе [Визуализатор параллелизма](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="252a0-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="252a0-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="252a0-112">See also</span></span>

- [<span data-ttu-id="252a0-113">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="252a0-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
