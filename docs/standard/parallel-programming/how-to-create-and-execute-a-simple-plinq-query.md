---
title: "How to: Create and Execute a Simple PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to create"
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Create and Execute a Simple PLINQ Query
В следующем примере показано, как создать простой параллельный запрос LINQ \(PLINQ\) с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A> исходной последовательности, а также выполнить запрос с помощью метода <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  
  
> [!NOTE]
>  В этой документации для определения делегатов в PLINQ используются лямбда\-выражения.  Сведения о лямбда\-выражениях в C\# или Visual Basic см. в разделе [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Пример  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 В данном примере показан базовый шаблон для создания и выполнения любого параллельного запроса LINQ в случае, когда порядок последовательности результатов не имеет значения; неупорядоченные запросы обычно выполняются быстрее упорядоченных.  Запрос делит источник на задачи, выполняемые асинхронно в нескольких потоках.  Порядок выполнения каждой из задач зависит не только от объема работы по обработке элементов в разделе, но и от внешних факторов, например, от планирования каждого из потоков операционной системой.  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects.  Дополнительные сведения о том, как ускорить его выполнение, см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  Дополнительные сведения о сохранении порядка элементов в запросе см. в разделе [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)