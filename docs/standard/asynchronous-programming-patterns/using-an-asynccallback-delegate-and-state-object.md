---
title: "Использование делегата AsyncCallback и объекта состояния"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a>Использование делегата AsyncCallback и объекта состояния
При использовании <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке, объект состояния можно использовать для передачи сведений между обратных вызовов и для получения окончательного результата. В этом разделе демонстрируется такой подход, развернув в примере в [использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен (DNS) для указанных пользователем компьютеров. В этом примере определяется и используется `HostRequest` класса для хранения сведений о состоянии. Объект `HostRequest` создается для каждого введенного пользователем имени компьютера. Этот объект передается <xref:System.Net.Dns.BeginGetHostByName%2A> метод. `ProcessDnsInformation` Метод вызывается каждый раз при завершении запроса. `HostRequest` Объект извлекается с помощью <xref:System.IAsyncResult.AsyncState%2A> свойство. `ProcessDnsInformation` Использует метод `HostRequest` объект для хранения <xref:System.Net.IPHostEntry> возвращаемых по запросу или <xref:System.Net.Sockets.SocketException> выводится запрос. После выполнения всех запросов приложение выполняет итерацию `HostRequest` объектов и отображает сведения о DNS или <xref:System.Net.Sockets.SocketException> сообщение об ошибке.  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
