---
title: "Using an AsyncCallback Delegate and State Object | Microsoft Docs"
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
  - "asynchronous programming, delegates"
  - "AsyncCallback delegate, samples"
  - "asynchronous programming, state objects"
  - "IAsyncResult interface, samples"
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Using an AsyncCallback Delegate and State Object
При использовании делегата <xref:System.AsyncCallback> для обработки результатов асинхронной операции в отдельном потоке, можно использовать объект состояния для передачи данных между обратными вызовами и извлечения конечного результата.  В этом разделе эта практика продемонстрирована на расширенном примере из [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## Пример  
 В следующем примере кода демонстрируется использование асинхронных методов класса <xref:System.Net.Dns> для извлечения сведений о службе доменных имен \(DNS\) для указанных пользователем компьютеров.  В этом примере определяется и используется класс `HostRequest` для хранения сведений о состоянии.  Объект `HostRequest` создается для каждого введенного пользователем имени компьютера.  Этот объект передается в метод <xref:System.Net.Dns.BeginGetHostByName%2A>.  Метод `ProcessDnsInformation` вызывается каждый раз по завершении выполнения запроса.  Объект `HostRequest` извлекается с использованием свойства <xref:System.IAsyncResult.AsyncState%2A>.  Метод `ProcessDnsInformation` использует объект `HostRequest` для хранения объекта <xref:System.Net.IPHostEntry>, возвращаемого запросом или исключением <xref:System.Net.Sockets.SocketException>, выданным этим запросом.  После завершения выполнения всех запросов приложение выполняет итерацию объектов `HostRequest` и выводит DNS\-данные или сообщение об ошибке <xref:System.Net.Sockets.SocketException>.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## См. также  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)