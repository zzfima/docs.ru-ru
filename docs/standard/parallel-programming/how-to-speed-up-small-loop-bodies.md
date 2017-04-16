---
title: "How to: Speed Up Small Loop Bodies | Microsoft Docs"
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
  - "parallel loops, how to speed up"
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# How to: Speed Up Small Loop Bodies
Когда цикл <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> имеет небольшое тело, он может выполняться значительно медленнее, чем эквивалентный последовательный цикл, такой как цикл [for](../Topic/for%20\(C%23%20Reference\).md) в C\# и цикл [For](http://msdn.microsoft.com/ru-ru/c470a263-9b49-4308-8fd6-8592b84a7980) в Visual Basic.  Снижение производительности происходит вследствие нагрузки, связанной с секционированием данных и стоимостью вызова делегата в каждой итерации цикла.  Для разрешения таких сценариев класс <xref:System.Collections.Concurrent.Partitioner> предоставляет метод <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=fullName>, который позволяет выполнять последовательный цикл для тела делегата, чтобы делегат вызывался только один раз для каждой секции, а не по разу в каждой итерации.  Дополнительные сведения см. в разделе [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Пример  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 Подход, продемонстрированный в данном примере, полезно использовать в тех случаях, когда цикл выполняет минимальный объем работ.  Когда работа начнет потреблять больше вычислительных ресурсов, возможно, вы получите такую же или более высокую производительность с помощью цикла <xref:System.Threading.Tasks.Parallel.For%2A> или <xref:System.Threading.Tasks.Parallel.ForEach%2A> с разделителем по умолчанию.  
  
## См. также  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)   
 [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)