---
title: "How to: Cancel a Task and Its Children | Microsoft Docs"
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
  - "tasks, how to cancel"
ms.assetid: 08574301-8331-4719-ad50-9cf7f6ff3048
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a Task and Its Children
В следующих примерах показано выполнение следующих задач.  
  
1.  Создание и запуск отменяемой задачи.  
  
2.  Передача токена отмены пользовательскому делегату и при необходимости экземпляру задачи.  
  
3.  Рассмотрение и ответ на запрос отмены в пользовательском делегате.  
  
4.  При необходимости проверка отмены задачи в вызывающем потоке.  
  
 Вызывающий поток не завершает задачу принудительно. Он только сообщает о запросе отмены.  Если задача уже выполняется, за рассмотрение запроса и соответствующую реакцию отвечает пользовательский делегат.  При запросе отмены до запуска задачи пользовательский делегат никогда не выполняется, и объект задачи переходит в состояние Canceled.  
  
## Пример  
 В этом примере показано, как завершить задачу <xref:System.Threading.Tasks.Task> и ее дочерние задачи в ответ на запрос отмены.  В нем также показано, что при завершении пользовательского делегата путем выдачи исключения <xref:System.Threading.Tasks.TaskCanceledException> вызывающий поток может дополнительно использовать метод <xref:System.Threading.Tasks.Task.Wait%2A> или метод <xref:System.Threading.Tasks.Task.WaitAll%2A> для ожидания завершения задач.  В этом случае вы должны использовать блок `try/catch` для обработки исключений в вызывающем потоке.  
  
 [!code-csharp[TPL_Cancellation#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/cancel1.cs#04)]
 [!code-vb[TPL_Cancellation#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/cancel1.vb#04)]  
  
 Класс <xref:System.Threading.Tasks.Task?displayProperty=fullName> полностью интегрирован с моделью отмены, основанной на типах <xref:System.Threading.CancellationTokenSource?displayProperty=fullName> и <xref:System.Threading.CancellationToken?displayProperty=fullName>.  Дополнительные сведения см. в разделах [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md) и [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).  
  
## См. также  
 <xref:System.Threading.CancellationTokenSource?displayProperty=fullName>   
 <xref:System.Threading.CancellationToken?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.Task%601?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)   
 [Attached and Detached Child Tasks](../../../docs/standard/parallel-programming/attached-and-detached-child-tasks.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)