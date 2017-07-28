---
title: "How to: Implement a Partitioner for Static Partitioning | Microsoft Docs"
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
  - "tasks, how to create a static partitioner"
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Implement a Partitioner for Static Partitioning
Следующий пример показывает один из способов реализации простого пользовательского модуля разделения для PLINQ, выполняющего статическое разделение.  Поскольку модуль разделения не поддерживает динамические разделы, он не поддерживается <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>.  Данный модуль разделения может обеспечить ускорение работы посредством модуля разделения по диапазонам по умолчанию для источников данных, для которых каждый элемент требует увеличение времени обработки.  
  
## Пример  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Разделы в данном примере основаны на предположительном линейном увеличении времени обработки для каждого элемента.  В реальной жизни может быть сложно спрогнозировать время обработки этим способом.  При использовании статического модуля разделения с указанным источником данных, можно оптимизировать формулу разделения для источника, добавить логику распределения нагрузки или использовать разделение по блокам, как показано в [How to: Implement Dynamic Partitions](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## См. также  
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)