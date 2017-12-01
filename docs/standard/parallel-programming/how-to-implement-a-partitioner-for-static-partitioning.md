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
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Практическое руководство. Реализация разделителя для статического секционирования
В следующем примере показано, как реализовать простой пользовательский разделитель для PLINQ, выполняющего статическое разделение. Поскольку разделитель не поддерживает динамические разделы, он не поддерживается из <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Данный модуль разделения может обеспечить ускорение работы посредством модуля разделения диапазона по умолчанию для источников данных, для которых каждый элемент требует увеличение времени обработки.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Разделы в данном примере основаны на предположении линейным ростом времени обработки для каждого элемента. В реальном мире может быть сложно спрогнозировать время обработки таким образом. При использовании статического модуля разделения с определенными источниками данных, можно оптимизировать формулу разделения для источника, добавить логику распределения нагрузки или использовать разделение по блокам, как показано в [как: реализация динамических разделов](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>См. также  
 [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
