---
title: "How to: Cancel a Parallel.For or ForEach Loop | Microsoft Docs"
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
  - "parallel foreach loop, how to cancel"
  - "parallel for loops, how to cancel"
ms.assetid: 9d19b591-ea95-4418-8ea7-b6266af9905b
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Cancel a Parallel.For or ForEach Loop
Методы <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> поддерживают отмену посредством использования токенов отмены.  Дополнительные сведения об отмене в целом см. в разделе [Отмена](../../../docs/standard/threading/cancellation-in-managed-threads.md).  В параллельном цикле пользователь указывает токен <xref:System.Threading.CancellationToken> для метода в параметре <xref:System.Threading.Tasks.ParallelOptions> и заключает параллельный вызов в блок try\-catch.  
  
## Пример  
 В следующем примере показано, как отменить вызов метода <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>.  Тот же подход можно применить к вызову <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>.  
  
 [!code-csharp[TPL_Parallel#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallel_cancel.cs#29)]
 [!code-vb[TPL_Parallel#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/cancelloop.vb#29)]  
  
 Токен, который сигнализирует об отмене, является тем же токеном, который указан в экземпляре <xref:System.Threading.Tasks.ParallelOptions>. Затем параллельный цикл создает одно исключение <xref:System.OperationCanceledException> при отмене.  Если отмену вызывает какой\-либо другой токен, цикл создаст исключение <xref:System.AggregateException> с <xref:System.OperationCanceledException> как InnerException.  
  
## См. также  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)