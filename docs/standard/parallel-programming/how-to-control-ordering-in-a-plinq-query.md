---
title: "How to: Control Ordering in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to control ordering"
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Control Ordering in a PLINQ Query
В этих примерах показано управление порядком в запросе PLINQ с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
> [!WARNING]
>  Эти примеры в основном демонстрируют использование и могут выполняться быстрее или медленнее, чем аналогичные последовательные запросы LINQ to Objects.  
  
## Пример  
 В следующем примере порядок исходной последовательности сохраняется.  Это иногда необходимо, например некоторые операторы запроса требуют упорядоченной исходной последовательности для получения правильных результатов.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## Пример  
 В следующем примере показаны некоторые операторы запроса, исходная последовательность которых будет упорядоченной.  Эти операторы будут работать с неупорядоченными последовательностями, но это может привести к непредсказуемым результатам.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в проекте [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите F5.  
  
## Пример  
 В следующем примере показано, как сохранить порядок первой части запроса, а затем удалить его для повышения производительности предложения join, после чего повторно применить порядок к конечной полученной последовательности.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в проекте [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md) и нажмите F5.  
  
## См. также  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)