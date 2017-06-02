---
title: "How to: Combine Parallel and Sequential LINQ Queries | Microsoft Docs"
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
  - "parallel queries, combine parallel and sequential"
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Combine Parallel and Sequential LINQ Queries
В этом примере показано, как использовать метод <xref:System.Linq.ParallelEnumerable.AsSequential%2A> для указания PLINQ последовательно обработать все последующие операторы в запросе.  Хотя обычно последовательная обработка медленнее, чем параллельная, иногда она требуется для получения правильных результатов.  
  
> [!WARNING]
>  Этот пример демонстрирует использование и может выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 В следующем примере показан один сценарий, в котором <xref:System.Linq.ParallelEnumerable.AsSequential%2A> необходим, а именно для сохранения порядка, установленного в предыдущем предложении запроса.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## Компиляция кода  
 Чтобы скомпилировать и запустить этот код, нужно вставить его в проект [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md), добавить строку для вызова метода из `Main` и нажать F5.  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)