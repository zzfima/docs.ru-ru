---
title: "Использование делегата AsyncCallback для завершения асинхронной операции"
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
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bbe170588776daa97fec4c736d4b1bdd871de518
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a>Использование делегата AsyncCallback для завершения асинхронной операции
Приложения, которые могут выполнять другую работу во время ожидания результатов асинхронной операции не должны блокировать ожидание до завершения операции. Для продолжения выполнения инструкций при ожидании завершения асинхронной операции, используйте один из следующих параметров:  
  
-   Используйте <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке. Этот подход демонстрируется в данном разделе.  
  
-   Используйте <xref:System.IAsyncResult.IsCompleted%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод, чтобы определить, завершена ли операция. Пример, демонстрирующий этот способ см. в разделе [запрос состояния асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен (DNS) для указанных пользователем компьютеров. В этом примере создается <xref:System.AsyncCallback> делегат, который ссылается `ProcessDnsInformation` метод. Этот метод вызывается один раз для каждого асинхронного запроса сведений DNS.  
  
 Обратите внимание, что передаваемый узла определяемый пользователем <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> параметра. Пример, демонстрирующий определения и использования более сложного объекта состояния см. в разделе [использование делегата AsyncCallback и объект состояния](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [Вызов асинхронных методов с помощью IAsyncResult](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [Использование делегата AsyncCallback и объекта состояния](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
