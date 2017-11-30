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
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="4855b-102">Блокирование выполнения приложения с помощью AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="4855b-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="4855b-103">Приложения, которые не могут продолжать выполнять другую работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="4855b-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="4855b-104">Используйте один из следующих параметров для блокирования основного потока приложения во время ожидания завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="4855b-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="4855b-105">Используйте <xref:System.IAsyncResult.AsyncWaitHandle%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод.</span><span class="sxs-lookup"><span data-stu-id="4855b-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method.</span></span> <span data-ttu-id="4855b-106">Этот подход демонстрируется в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="4855b-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="4855b-107">Вызов асинхронной операции **окончания** *Имя_операции* метод.</span><span class="sxs-lookup"><span data-stu-id="4855b-107">Call the asynchronous operation's **End** *OperationName* method.</span></span> <span data-ttu-id="4855b-108">Пример, демонстрирующий этот способ см. в разделе [блокирование выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4855b-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="4855b-109">Приложения, использующие один или несколько <xref:System.Threading.WaitHandle> объектов для блокирования до завершения асинхронной операции будет вызывать **начать** *Имя_операции* метода выполняют работу, которую можно сделать Завершает набор команд без результатов операции, а затем блок до выполнения асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="4855b-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin** *OperationName* method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="4855b-110">Приложение может блокировать в одной операции путем вызова одного из <xref:System.Threading.WaitHandle.WaitOne%2A> методы с использованием <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="4855b-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="4855b-111">На время ожидания для набора завершения асинхронных операций, сохраните связанные <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекты в массиве и вызовите один из <xref:System.Threading.WaitHandle.WaitAll%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="4855b-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="4855b-112">На время ожидания для любого набора завершения асинхронных операций, сохраните связанные <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекты в массиве и вызовите один из <xref:System.Threading.WaitHandle.WaitAny%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="4855b-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4855b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4855b-113">Example</span></span>  
 <span data-ttu-id="4855b-114">В следующем примере кода показано использование асинхронных методов в классе DNS для получения сведений о системе доменных имен для компьютера, заданного пользователем.</span><span class="sxs-lookup"><span data-stu-id="4855b-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="4855b-115">В примере демонстрируется блокирование с помощью <xref:System.Threading.WaitHandle> связанные с асинхронной операцией.</span><span class="sxs-lookup"><span data-stu-id="4855b-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="4855b-116">Обратите внимание, что `null` (`Nothing` в Visual Basic) передается <xref:System.Net.Dns.BeginGetHostByName%2A> `requestCallback` и `stateObject` параметры так, как они не являются обязательными при использовании такого подхода.</span><span class="sxs-lookup"><span data-stu-id="4855b-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4855b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4855b-117">See Also</span></span>  
 [<span data-ttu-id="4855b-118">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="4855b-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="4855b-119">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="4855b-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
