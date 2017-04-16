---
title: "How to: Listen for Cancellation Requests by Polling | Microsoft Docs"
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
  - "cancellation, how to poll for requests"
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Listen for Cancellation Requests by Polling
В следующем примере показан один способ, которым пользовательский код может выполнять опрос токена отмены через определенные интервалы времени, чтобы узнать, не запросил ли вызывающий поток отмену.  В примере используется тип <xref:System.Threading.Tasks.Task?displayProperty=fullName>. Следует учитывать, что эта модель также применима и к асинхронным операциям, созданным непосредственно типом <xref:System.Threading.ThreadPool?displayProperty=fullName> или типом <xref:System.Threading.Thread?displayProperty=fullName>.  
  
## Пример  
 Для выполнения опроса необходим циклический или рекурсивный код, который может периодически считывать значение логического свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>.  Если используется тип <xref:System.Threading.Tasks.Task?displayProperty=fullName> и ожидается завершение задачи вызывающим потоком, то с помощью метода <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> можно проверять значение свойства и создавать исключение.  С помощью этого метода можно обеспечить создание правильного исключения в ответ на запрос.  Если используется тип <xref:System.Threading.Tasks.Task>, то вызов этого метода предпочтительнее, чем создание исключения <xref:System.OperationCanceledException> вручную.  Если создавать исключение не планируется, то можно ограничиться проверкой значения этого свойства и возвратом из метода, если свойство имеет значение `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Вызов метода <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> выполняется очень быстро и не вносит в циклы существенную нагрузку.  
  
 Если помимо создания исключения имеется другая работа, которую следует выполнять в ответ на отмену, то при вызове метода <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> достаточно явно проверить значение свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>.  Как можно заметить, в данном примере код действительно получает доступ к свойству дважды: один раз явно и второй раз в методе <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>.  Но поскольку в действии по считыванию свойства <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> используется только одна временная инструкция чтения для каждого доступа, такой двойной доступ не оказывает существенного влияния на производительность.  Кроме того, вызов этого метода все же предпочтительнее, чем создание исключения <xref:System.OperationCanceledException> вручную.  
  
## См. также  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)