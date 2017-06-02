---
title: "How to: Specify Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use merge options"
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Specify Merge Options in PLINQ
В этом примере показано, как указать параметры слияния, которые будут применяться ко всем последующим операторам в запросе PLINQ.  Нет необходимости задавать параметры слияния явно, но это может повысить производительность.  Дополнительные сведения о параметрах слияния см. в разделе [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
> [!WARNING]
>  Этот пример демонстрирует использование и может выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 В следующем примере демонстрируется поведение параметров слияния в основном сценарии, который имеет неупорядоченный источник и применяет ресурсоемкую функцию к каждому элементу.  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 В случаях, когда параметр <xref:System.Linq.ParallelMergeOptions> приводит к нежелательной задержке перед получением первого элемента, попробуйте использовать параметр <xref:System.Linq.ParallelMergeOptions>, чтобы получить результирующие элементы быстро и беспрепятственно.  
  
## См. также  
 <xref:System.Linq.ParallelMergeOptions>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)