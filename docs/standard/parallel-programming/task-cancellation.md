---
title: "Task Cancellation | Microsoft Docs"
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
  - "tasks, cancellation"
  - "asynchronous task cancellation"
ms.assetid: 3ecf1ea9-e399-4a6a-a0d6-8475f48dcb28
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Task Cancellation
Классы <xref:System.Threading.Tasks.Task?displayProperty=fullName> и <xref:System.Threading.Tasks.Task%601?displayProperty=fullName> поддерживают отмену с помощью токенов отмены в .NET Framework. Для получения дополнительной информации см. [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md). В классах задач отмена включает взаимодействие между пользовательским делегатом, который представляет операцию отмены, и кодом, который запросил отмену.  Успешная отмена включает запрашивающий код, вызывающий метод <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName>, и пользовательский делегат, своевременно завершающий операцию. Операцию можно завершить одним из следующих способов.  
  
-   Путем простого возврата из делегата. Во многих сценариях этого достаточно, однако экземпляр задачи, отмененный таким образом, переходит в состояние <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>, а не в состояние <xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>.  
  
-   Путем создания исключения <xref:System.OperationCanceledException> и его передачи в токен, на котором была запрошена отмена. Предпочтительным способом сделать это является использование метода <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>. Задача, отмененная таким образом, переходит в состояние Canceled, которое вызывающий код может использовать для проверки того, что задача ответила на запрос на отмену.  
  
 В следующем примере показан базовый шаблон для отмены задачи, вызвавшей исключение. Обратите внимание, что токен передается пользовательскому делегату и самому экземпляру задачи.  
  
 [!code-csharp[TPL_Cancellation#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_cancellation/cs/snippet02.cs#02)]
 [!code-vb[TPL_Cancellation#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_cancellation/vb/module1.vb#02)]  
  
 Более полный пример содержится в разделе [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
 Когда экземпляр задачи обнаруживает исключение <xref:System.OperationCanceledException>, созданное пользовательским кодом, он сравнивает токен исключения со связанным токеном \(переданным в API\-интерфейс, в котором была создана задача\). Если они совпадают и свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена возвращает значение true, задача интерпретирует это как подтверждение отмены и переходит в состояние Canceled. Если метод <xref:System.Threading.Tasks.Task.Wait%2A> или <xref:System.Threading.Tasks.Task.WaitAll%2A> не используется для ожидания задачи, она просто устанавливает состояние <xref:System.Threading.Tasks.TaskStatus>.  
  
 Если ожидается задача, которая переходит в состояние Canceled, создается исключение <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=fullName> \(заключенное в исключение <xref:System.AggregateException>\). Обратите внимание, что это исключение указывает на успешную отмену, а не на сбой. Следовательно, свойство <xref:System.Threading.Tasks.Task.Exception%2A> задачи возвращает значение `null`.  
  
 Если свойство <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> токена возвращает значение false или если токен исключения не соответствует токену задачи, исключение <xref:System.OperationCanceledException> обрабатывается как обычное исключение, вызывая переход задачи в состояние Faulted. Кроме того, обратите внимание, что наличие других исключений также приведет к переходу задачи в состояние Faulted. Состояние завершения задачи можно получить в свойстве <xref:System.Threading.Tasks.Task.Status%2A>.  
  
 В некоторых случаях задача может продолжить обработку некоторых элементов после запроса отмены.  
  
## См. также  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)   
 [How to: Cancel a Task and Its Children](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)