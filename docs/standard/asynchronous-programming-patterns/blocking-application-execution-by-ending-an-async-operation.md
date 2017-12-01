---
title: "Блокировка выполнения приложения путем завершения асинхронной операции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.openlocfilehash: ccca6e1e4f6b5cdf098018b59426fb2262e2b346
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a>Блокировка выполнения приложения путем завершения асинхронной операции
Приложения, которые не могут продолжать выполнять другую работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения операции. Используйте один из следующих параметров для блокирования основного потока приложения во время ожидания завершения асинхронной операции.  
  
-   Вызов асинхронных операций **окончания** *Имя_операции* метод. Этот подход демонстрируется в данном разделе.  
  
-   Используйте <xref:System.IAsyncResult.AsyncWaitHandle%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод. Пример, демонстрирующий этот способ см. в разделе [блокировки приложения выполнения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).  
  
 Приложения, использующие **окончания** *OperationName* будет вызывать метод для блокирования до завершения асинхронной операции **начать**  *Имя_операции* метода выполняют работу, которую можно выполнить без результатов операции, а затем вызвать **окончания** *Имя_операции*.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен для компьютера, заданного пользователем. Обратите внимание, что `null` (`Nothing` в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` и `stateObject` параметры так, как эти параметры не являются обязательными при использовании такого подхода.  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
