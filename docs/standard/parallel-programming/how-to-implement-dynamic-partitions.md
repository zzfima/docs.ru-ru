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
# <a name="how-to-implement-dynamic-partitions"></a>Практическое руководство. Реализация динамических разделов
В следующем примере показано, как реализовать пользовательский <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> , реализует динамическое секционирование и может использоваться посредством определенных перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и PLINQ.  
  
## <a name="example"></a>Пример  
 Каждый раз раздел вызывает <xref:System.Collections.IEnumerator.MoveNext%2A> в перечислителе, перечислитель предоставляет раздел с одним элементом списка. В случае с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A>, секция является <xref:System.Threading.Tasks.Task> экземпляра. Поскольку запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизируется.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Это пример разделения по блокам, где каждый блок состоит из одного элемента. Предоставляя несколько элементов одновременно, можно уменьшить конфликты через блокировку и теоретически увеличить производительность. Однако в определенный момент большими частями может потребоваться дополнительная логика балансировки нагрузки для поддержания нагрузки всех потоков до завершения всех действий.  
  
## <a name="see-also"></a>См. также  
 [Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)  
 [Практическое руководство. Реализация разделителя для статического секционирования](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
