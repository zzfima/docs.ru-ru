---
title: "Блокирование выполнения приложения с помощью AsyncWaitHandle"
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
- blocks, asynchronous operations
- ending asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming, blocking applications
- stopping asynchronous operations
- blocking application execution
ms.assetid: 3e32daf2-8161-4e8f-addd-9fd9ff101b03
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2660b3cbf7e8ee43a22edbfb66a4262684983b87
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a>Блокирование выполнения приложения с помощью AsyncWaitHandle
Приложения, которые не могут продолжать выполнять другую работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения операции. Используйте один из следующих параметров для блокирования основного потока приложения во время ожидания завершения асинхронной операции.  
  
-   Используйте <xref:System.IAsyncResult.AsyncWaitHandle%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод. Этот подход демонстрируется в данном разделе.  
  
-   Вызов асинхронной операции **окончания** *Имя_операции* метод. Пример, демонстрирующий этот способ см. в разделе [блокирование выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).  
  
 Приложения, использующие один или несколько <xref:System.Threading.WaitHandle> объектов для блокирования до завершения асинхронной операции будет вызывать **начать** *Имя_операции* метода выполняют работу, которую можно сделать Завершает набор команд без результатов операции, а затем блок до выполнения асинхронных операций. Приложение может блокировать в одной операции путем вызова одного из <xref:System.Threading.WaitHandle.WaitOne%2A> методы с использованием <xref:System.IAsyncResult.AsyncWaitHandle%2A>. На время ожидания для набора завершения асинхронных операций, сохраните связанные <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекты в массиве и вызовите один из <xref:System.Threading.WaitHandle.WaitAll%2A> методы. На время ожидания для любого набора завершения асинхронных операций, сохраните связанные <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекты в массиве и вызовите один из <xref:System.Threading.WaitHandle.WaitAny%2A> методы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование асинхронных методов в классе DNS для получения сведений о системе доменных имен для компьютера, заданного пользователем. В примере демонстрируется блокирование с помощью <xref:System.Threading.WaitHandle> связанные с асинхронной операцией. Обратите внимание, что `null` (`Nothing` в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` и `stateObject` параметры так, как они не являются обязательными при использовании такого подхода.  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
