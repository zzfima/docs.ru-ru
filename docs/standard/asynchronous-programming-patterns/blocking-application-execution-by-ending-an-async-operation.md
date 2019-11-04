---
title: Блокировка выполнения приложения путем завершения асинхронной операции
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- blocks, asynchronous operations
- AsyncWaitHandle property
- asynchronous programming, blocking applications
- blocking application execution
ms.assetid: cc5e2834-a65b-4df8-b750-7bdb79997fee
dev_langs:
- csharp
- vb
ms.openlocfilehash: aed3b18c154d4b7a4390b28fb1f14536690f6b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121329"
---
# <a name="blocking-application-execution-by-ending-an-async-operation"></a><span data-ttu-id="b9d7d-102">Блокировка выполнения приложения путем завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="b9d7d-102">Blocking Application Execution by Ending an Async Operation</span></span>
<span data-ttu-id="b9d7d-103">Приложения, которые не могут продолжать работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="b9d7d-104">Используйте один из следующих вариантов, чтобы блокировать основной поток приложения на период ожидания асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="b9d7d-105">Вызовите метод **End**_имя_операции_ асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-105">Call the asynchronous operations **End**_OperationName_ method.</span></span> <span data-ttu-id="b9d7d-106">Именно этот подход демонстрируется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="b9d7d-107">Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin**_имя_операции_ асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-107">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="b9d7d-108">Пример с демонстрацией этого подхода см. в статье [Блокирование выполнения приложения с помощью AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="b9d7d-108">For an example that demonstrates this approach, see [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
 <span data-ttu-id="b9d7d-109">Приложения, использующие метод **End**_имя_операции_, чтобы блокировать выполнение до завершения асинхронной операции, обычно вызывают метод **Begin**_имя_операции_, затем выполняют все, что можно сделать без результатов этой операции и вызывают метод **End**_имя_операции_.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-109">Applications that use the **End**_OperationName_ method to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then call **End**_OperationName_.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9d7d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b9d7d-110">Example</span></span>  
 <span data-ttu-id="b9d7d-111">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-111">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="b9d7d-112">Обратите внимание, что в параметрах <xref:System.Net.Dns.BeginGetHostByName%2A>, `requestCallback` и `stateObject` передается значение `null` (`Nothing` в Visual Basic), так как при таком подходе эти аргументы не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="b9d7d-112">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these arguments are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlock.cs#1)]
 [!code-vb[AsyncDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9d7d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9d7d-113">See also</span></span>

- [<span data-ttu-id="b9d7d-114">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="b9d7d-114">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="b9d7d-115">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="b9d7d-115">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
