---
title: "Using an AsyncCallback Delegate to End an Asynchronous Operation | Microsoft Docs"
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
  - "ending asynchronous operations"
  - "asynchronous programming, ending operations"
  - "AsyncCallback delegate"
  - "stopping asynchronous operations"
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Using an AsyncCallback Delegate to End an Asynchronous Operation
Приложения, которые могут в ходе ожидания результатов выполнения асинхронной операции, не должны блокировать ожидание до завершения операции.  Для продолжения выполнения инструкций при ожидании завершения выполнения асинхронной операции выполните следующие действия:  
  
-   Для обработки результатов асинхронной операции в отдельном потоке используется делегат <xref:System.AsyncCallback>.  Этот способ демонстрируется в данном разделе.  
  
-   Для определения того, завершена ли асинхронная операция, используется свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin** *OperationName* этой операции.  Пример, демонстрирующий этот подход, см. в разделе [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## Пример  
 В следующем примере кода демонстрируется использование асинхронных методов класса <xref:System.Net.Dns> для извлечения сведений о службе доменных имен \(DNS\) для указанных пользователем компьютеров.  В этом примере создается делегат <xref:System.AsyncCallback>, который представляет метод `ProcessDnsInformation`.  Этот метод вызывается один раз для каждого асинхронного запроса сведений о DNS.  
  
 Обратите внимание, что указанное пользователем основное приложение передается в параметр <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object>.  Пример определения и использования более сложного объекта состояния см. в разделе [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## См. также  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Calling Asynchronous Methods Using IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)   
 [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)