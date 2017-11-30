---
title: "Практическое руководство. Реализация разделителя для статического секционирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a><span data-ttu-id="6a658-102">Практическое руководство. Реализация разделителя для статического секционирования</span><span class="sxs-lookup"><span data-stu-id="6a658-102">How to: Implement a Partitioner for Static Partitioning</span></span>
<span data-ttu-id="6a658-103">В следующем примере показано, как реализовать простой пользовательский разделитель для PLINQ, выполняющего статическое разделение.</span><span class="sxs-lookup"><span data-stu-id="6a658-103">The following example shows one way to implement a simple custom partitioner for PLINQ that performs static partitioning.</span></span> <span data-ttu-id="6a658-104">Поскольку разделитель не поддерживает динамические разделы, он не поддерживается из <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6a658-104">Because the partitioner does not support dynamic partitions, it is not consumable from <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6a658-105">Данный модуль разделения может обеспечить ускорение работы посредством модуля разделения диапазона по умолчанию для источников данных, для которых каждый элемент требует увеличение времени обработки.</span><span class="sxs-lookup"><span data-stu-id="6a658-105">This particular partitioner might provide speedup over the default range partitioner for data sources for which each element requires an increasing amount of processing time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a658-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6a658-106">Example</span></span>  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 <span data-ttu-id="6a658-107">Разделы в данном примере основаны на предположении линейным ростом времени обработки для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="6a658-107">The partitions in this example are based on the assumption of a linear increase in processing time for each element.</span></span> <span data-ttu-id="6a658-108">В реальном мире может быть сложно спрогнозировать время обработки таким образом.</span><span class="sxs-lookup"><span data-stu-id="6a658-108">In the real world, it might be difficult to predict processing times in this way.</span></span> <span data-ttu-id="6a658-109">При использовании статического модуля разделения с определенными источниками данных, можно оптимизировать формулу разделения для источника, добавить логику распределения нагрузки или использовать разделение по блокам, как показано в [как: реализация динамических разделов](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="6a658-109">If you are using a static partitioner with a specific data source, you can optimize the partitioning formula for the source, add load-balancing logic, or use a chunk partitioning approach as demonstrated in [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a658-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6a658-110">See Also</span></span>  
 [<span data-ttu-id="6a658-111">Пользовательские разделители для PLINQ и TPL</span><span class="sxs-lookup"><span data-stu-id="6a658-111">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
