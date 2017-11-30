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
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="1f252-102">Блокировка выполнения приложения путем завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="1f252-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="1f252-103">Приложения, которые не могут продолжать выполнять другую работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="1f252-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="1f252-104">Используйте один из следующих параметров для блокирования основного потока приложения во время ожидания завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1f252-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="1f252-105">Вызов асинхронных операций **окончания** *Имя_операции* метод.</span><span class="sxs-lookup"><span data-stu-id="1f252-105">Call the asynchronous operations **End** *OperationName* method.</span></span> <span data-ttu-id="1f252-106">Этот подход демонстрируется в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="1f252-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="1f252-107">Используйте <xref:System.IAsyncResult.AsyncWaitHandle%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод.</span><span class="sxs-lookup"><span data-stu-id="1f252-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="1f252-108">Пример, демонстрирующий этот способ см. в разделе [блокировки приложения выполнения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="1f252-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="1f252-109">Приложения, использующие **окончания** *OperationName* будет вызывать метод для блокирования до завершения асинхронной операции **начать**  *Имя_операции* метода выполняют работу, которую можно выполнить без результатов операции, а затем вызвать **окончания** *Имя_операции*.</span><span class="sxs-lookup"><span data-stu-id="1f252-109">Applications that use the **End** *OperationName* method to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then call **End** *OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f252-110">Пример</span><span class="sxs-lookup"><span data-stu-id="1f252-110">Example</span></span>  
 <span data-ttu-id="1f252-111">В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен для компьютера, заданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="1f252-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="1f252-112">Обратите внимание, что `null` (`Nothing` в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` и `stateObject` параметры так, как эти параметры не являются обязательными при использовании такого подхода.</span><span class="sxs-lookup"><span data-stu-id="1f252-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1f252-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1f252-113">See Also</span></span>  
 [<span data-ttu-id="1f252-114">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="1f252-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="1f252-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="1f252-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
