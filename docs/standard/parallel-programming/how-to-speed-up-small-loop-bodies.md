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
# <a name="how-to-speed-up-small-loop-bodies"></a>Практическое руководство. Повышение скорости выполнения небольших тел циклов
Когда <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> цикл имеет небольшое тело, он может выполняться медленнее, чем эквивалентный последовательный цикл, таких как [для](~/docs/csharp/language-reference/keywords/for.md) в C# и [для](http://msdn.microsoft.com/en-us/c470a263-9b49-4308-8fd6-8592b84a7980) цикл в Visual Basic. Снижение производительности происходит вследствие нагрузки, связанной с секционированием данных и стоимостью вызова делегата в каждой итерации цикла. Для разрешения таких сценариев класс <xref:System.Collections.Concurrent.Partitioner> предоставляет метод <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType>, который позволяет выполнять последовательный цикл для тела делегата, чтобы делегат вызывался только один раз для каждой секции, а не по разу в каждой итерации. Дополнительные сведения см. в разделе [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Подход, продемонстрированный в данном примере, полезно использовать в тех случаях, когда цикл выполняет минимальный объем работ. Когда работа начнет потреблять больше вычислительных ресурсов, возможно, вы получите такую же или более высокую производительность с помощью цикла <xref:System.Threading.Tasks.Parallel.For%2A> или <xref:System.Threading.Tasks.Parallel.ForEach%2A> с разделителем по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
