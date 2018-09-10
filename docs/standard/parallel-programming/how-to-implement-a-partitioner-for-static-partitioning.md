---
title: Практическое руководство. Реализация разделителя для статического секционирования
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 302d7d98d04e528d205edf38c3fa13bb3f2b2252
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863077"
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="93dc0-102">Практическое руководство. Реализация разделителя для статического секционирования</span><span class="sxs-lookup"><span data-stu-id="93dc0-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="93dc0-103">Следующий пример демонстрирует реализацию простого пользовательского разделителя для PLINQ, который выполняет статическое секционирование.</span><span class="sxs-lookup"><span data-stu-id="93dc0-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="93dc0-104">Поскольку этот разделитель не поддерживает динамические секции, его нельзя использовать в <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93dc0-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="93dc0-105">Эта конкретная реализация разделителя может работать быстрее, чем стандартный разделитель по диапазонам для таких источников данных, в которых требуется большое время на обработку каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="93dc0-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93dc0-106">Пример</span><span class="sxs-lookup"><span data-stu-id="93dc0-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="93dc0-107">Секции в этом примере создаются, исходя из предположения о линейном увеличении времени обработки для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="93dc0-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="93dc0-108">В реальных ситуациях обычно нельзя так просто спрогнозировать время обработки.</span><span class="sxs-lookup"><span data-stu-id="93dc0-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="93dc0-109">Если вы используете статический разделитель для конкретного источника данных, попробуйте оптимизировать формулу разделения для этого источника, добавить логику балансировки нагрузки или использовать блочное секционирование. Примеры таких подходов представлены в статье [Практическое руководство. Реализация динамических секций](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="93dc0-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93dc0-110">См. также</span><span class="sxs-lookup"><span data-stu-id="93dc0-110">See also</span></span>

- [<span data-ttu-id="93dc0-111">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="93dc0-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
