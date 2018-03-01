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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
dev_langs:
- csharp
- vb
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ec7bfe6fe2cef20a6d74030802113a47e8679e1
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2018
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="13707-102">Блокировка выполнения приложения путем завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="13707-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="13707-103">Приложения, которые не могут продолжать работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="13707-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="13707-104">Используйте один из следующих вариантов, чтобы блокировать основной поток приложения на период ожидания асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="13707-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="13707-105">Вызовите метод **End***имя_операции* асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="13707-105">Call the asynchronous operations **End***OperationName* method.</span></span> <span data-ttu-id="13707-106">Именно этот подход демонстрируется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="13707-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="13707-107">Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin***имя_операции* асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="13707-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method.</span></span> <span data-ttu-id="13707-108">Пример с демонстрацией этого подхода см. в статье [Блокирование выполнения приложения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="13707-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="13707-109">Приложения, использующие метод **End***имя_операции*, чтобы блокировать выполнение до завершения асинхронной операции, обычно вызывают метод **Begin***имя_операции*, затем выполняют все, что можно сделать без результатов этой операции и вызывают метод **End***имя_операции*.</span><span class="sxs-lookup"><span data-stu-id="13707-109">Applications that use the **End***OperationName* method to block until an asynchronous operation is complete will typically call the **Begin***OperationName* method, perform any work that can be done without the results of the operation, and then call **End***OperationName*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13707-110">Пример</span><span class="sxs-lookup"><span data-stu-id="13707-110">Example</span></span>  
 <span data-ttu-id="13707-111">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере.</span><span class="sxs-lookup"><span data-stu-id="13707-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="13707-112">Обратите внимание, что в параметрах <xref:System.Net.Dns.BeginGetHostByName%2A>, `requestCallback` и `stateObject` передается значение `null` (`Nothing` в Visual Basic), так как при таком подходе эти аргументы не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="13707-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="13707-113">См. также</span><span class="sxs-lookup"><span data-stu-id="13707-113">See Also</span></span>  
 [<span data-ttu-id="13707-114">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="13707-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="13707-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="13707-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
