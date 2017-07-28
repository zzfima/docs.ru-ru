---
title: "How to: Implement Dynamic Partitions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, how to create a dynamic partitioner"
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# How to: Implement Dynamic Partitions
Следующий пример показывает реализацию пользовательского <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=fullName>, который осуществляет динамическое разделение и может использоваться посредством определенных перегрузок <xref:System.Threading.Tasks.Parallel.ForEach%2A> и PLINQ.  
  
## Пример  
 Каждый раз раздел вызывает <xref:System.Collections.IEnumerator.MoveNext%2A> в перечислителе, перечислитель предоставляет раздел с одним элементом списка.  В случае с PLINQ и <xref:System.Threading.Tasks.Parallel.ForEach%2A>, раздел является экземпляром <xref:System.Threading.Tasks.Task>.  За счет того, что запросы возникают параллельно в нескольких потоках, доступ к текущему индексу синхронизирован.  
  
 [!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#04)]
 [!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  
  
 Это пример разделения по блокам, где каждый блок состоит из одного элемента.  Предоставляя одновременно большее количество элементов можно снизить количество конфликтов посредством их блокирования и теоретически увеличить производительность.  Однако в тоже самое время, большие по размеру блоки требуют дополнительной логики при распределении нагрузки, для поддержания нагрузки всех потоков до полного завершения работы.  
  
## См. также  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [How to: Implement a Partitioner for Static Partitioning](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)