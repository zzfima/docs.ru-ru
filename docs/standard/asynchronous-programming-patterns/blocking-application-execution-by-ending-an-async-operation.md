---
title: "Blocking Application Execution by Ending an Async Operation | Microsoft Docs"
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
  - "blocks, asynchronous operations"
  - "AsyncWaitHandle property"
  - "asynchronous programming, blocking applications"
  - "blocking application execution"
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Blocking Application Execution by Ending an Async Operation
Приложения, которые не могут продолжать выполнение другой работы во время ожидания результатов асинхронной операции, должны блокироваться до момента завершения этой операции.  Для блокирования главного потока приложения на время ожидания завершения асинхронной операции используется один из следующих способов.  
  
-   Вызовите метод **End** *OperationName* асинхронной операции.  Этот способ демонстрируется в данном разделе.  
  
-   Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом асинхронной операции **Begin** *OperationName*.  Пример, демонстрирующий этот способ, см. в разделе [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Приложения, использующие метод **End** *OperationName* для блокировки до момента завершения асинхронной операции, обычно вызывают метод **Begin** *OperationName*, выполняют работу, которую можно сделать, не имея результатов операции, а затем вызывают метод **End** *OperationName*.  
  
## Пример  
 В следующем примере кода показано использование асинхронных методов в классе <xref:System.Net.Dns> для получения сведений службы доменных имен \(DNS\) для компьютера, заданного пользователем.  Заметьте, что в параметрах `requestCallback` и `stateObject` методу <xref:System.Net.Dns.BeginGetHostByName%2A> передается значение `null` \(`Nothing` в Visual Basic\), поскольку эти параметры не являются обязательными для такого способа блокировки.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## См. также  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)