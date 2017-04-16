---
title: "How to: Specify the Execution Mode in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to use execution mode"
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Specify the Execution Mode in PLINQ
В этом примере показан способ принудительного обхода PLINQ его эвристики по умолчанию и параллелизации запроса независимо от формы запроса.  
  
> [!WARNING]
>  Этот пример демонстрирует использование и может выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ предназначен для использования возможностей параллелизации.  Однако не все запросы лучше выполнять параллельно.  Например, если запрос содержит отдельный пользовательский делегат, который выполняет мало работы, запрос обычно выполняется быстрее последовательно.  Это происходит потому, что для выполнения параллелизации требуется больше ресурсов, чем для полученного ускорения.  Таким образом, PLINQ не выполняет параллелизацию каждого запроса автоматически.  Он сначала проверяет форму запроса и входящие в него различные операторы.  На основе этого анализа PLINQ в режиме выполнения по умолчанию может потребоваться выполнить некоторые части или весь запрос последовательно.  Однако в некоторых случаях о запросе может быть известно больше, чем PLINQ способен определить на основе анализа.  Например, может быть известно, что делегат требует большого количества ресурсов и что запрос определенно лучше обрабатывать параллельно.  В таких случаях можно использовать метод <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> и указать значение <xref:System.Linq.ParallelExecutionMode>, чтобы PLINQ всегда выполнял запрос параллельно.  
  
## Компиляция кода  
 Вырежьте и вставьте этот код в [PLINQ Data Sample](../../../docs/standard/parallel-programming/plinq-data-sample.md), и вызовите метод из `Main`.  
  
## См. также  
 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)