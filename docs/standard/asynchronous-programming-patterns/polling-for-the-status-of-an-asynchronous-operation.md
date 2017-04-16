---
title: "Polling for the Status of an Asynchronous Operation | Microsoft Docs"
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
  - "asynchronous programming, status polling"
  - "polling asynchronous operation status"
  - "status information [.NET Framework], asynchronous operations"
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Polling for the Status of an Asynchronous Operation
Приложения, которые могут в ходе ожидания результатов выполнения асинхронной операции, не должны блокировать ожидание до завершения операции.  Для продолжения выполнения инструкций при ожидании завершения выполнения асинхронной операции выполните следующие действия:  
  
-   Для определения того, завершена ли асинхронная операция, используется свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin** *OperationName* этой операции.  Такой подход известен как запрос, а его применение демонстрируется в этом разделе.  
  
-   Для обработки результатов асинхронной операции в отдельном потоке используется делегат <xref:System.AsyncCallback>.  Пример, демонстрирующий этот способ, см. в разделе [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Пример  
 В следующем примере кода показано использование асинхронных методов в классе <xref:System.Net.Dns> для получения сведений службы доменных имен \(DNS\) для компьютера, заданного пользователем.  В этом примере запускается асинхронная операция, затем в консоли выводятся точки \("."\), пока операция не будет завершена.  Обратите внимание, что **null** \(**Nothing** в Visual Basic\) передается в параметры <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> и <xref:System.Object>, так как эти аргументы при использовании этого подхода не требуются.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## См. также  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)