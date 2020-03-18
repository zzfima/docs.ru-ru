---
title: Блокирование выполнения приложения с помощью AsyncWaitHandle
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 16b5a297c13cd9096548ed489e4994b72a48da67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121424"
---
# <a name="blocking-application-execution-using-an-asyncwaithandle"></a><span data-ttu-id="1cc85-102">Блокирование выполнения приложения с помощью AsyncWaitHandle</span><span class="sxs-lookup"><span data-stu-id="1cc85-102">Blocking Application Execution Using an AsyncWaitHandle</span></span>
<span data-ttu-id="1cc85-103">Приложения, которые не могут продолжать работу во время ожидания результатов асинхронной операции, должны блокироваться до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="1cc85-103">Applications that cannot continue to do other work while waiting for the results of an asynchronous operation must block until the operation completes.</span></span> <span data-ttu-id="1cc85-104">Используйте один из следующих вариантов, чтобы блокировать основной поток приложения на период ожидания асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1cc85-104">Use one of the following options to block your application's main thread while waiting for an asynchronous operation to complete:</span></span>  
  
- <span data-ttu-id="1cc85-105">Используйте свойство <xref:System.IAsyncResult.AsyncWaitHandle%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin**_имя_операции_ асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1cc85-105">Use the <xref:System.IAsyncResult.AsyncWaitHandle%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin**_OperationName_ method.</span></span> <span data-ttu-id="1cc85-106">Именно этот подход демонстрируется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="1cc85-106">This approach is demonstrated in this topic.</span></span>  
  
- <span data-ttu-id="1cc85-107">Вызовите метод **End**_имя_операции_ асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="1cc85-107">Call the asynchronous operation's **End**_OperationName_ method.</span></span> <span data-ttu-id="1cc85-108">Пример с демонстрацией этого подхода см. в статье [Блокировка выполнения приложения путем завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span><span class="sxs-lookup"><span data-stu-id="1cc85-108">For an example that demonstrates this approach, see [Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
 <span data-ttu-id="1cc85-109">Приложения, использующие один или несколько объектов <xref:System.Threading.WaitHandle>, чтобы блокировать выполнение до завершения асинхронной операции, обычно вызывают метод **Begin**_имя_операции_, затем выполняют все, что можно сделать без результатов этой операции и блокируются до завершения асинхронных операций.</span><span class="sxs-lookup"><span data-stu-id="1cc85-109">Applications that use one or more <xref:System.Threading.WaitHandle> objects to block until an asynchronous operation is complete will typically call the **Begin**_OperationName_ method, perform any work that can be done without the results of the operation, and then block until the asynchronous operation(s) completes.</span></span> <span data-ttu-id="1cc85-110">Чтобы заблокировать приложение в ожидании одной операции, вызовите один из методов <xref:System.Threading.WaitHandle.WaitOne%2A> с использованием <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cc85-110">An application can block on a single operation by calling one of the <xref:System.Threading.WaitHandle.WaitOne%2A> methods using the <xref:System.IAsyncResult.AsyncWaitHandle%2A>.</span></span> <span data-ttu-id="1cc85-111">Чтобы заблокировать приложение в ожидании нескольких асинхронных операций, сохраните соответствующие объекты <xref:System.IAsyncResult.AsyncWaitHandle%2A> в массиве и вызовите один из методов <xref:System.Threading.WaitHandle.WaitAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cc85-111">To block while waiting for a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAll%2A> methods.</span></span> <span data-ttu-id="1cc85-112">Чтобы заблокировать приложение в ожидании одной из нескольких асинхронных операций, сохраните соответствующие объекты <xref:System.IAsyncResult.AsyncWaitHandle%2A> в массиве и вызовите один из методов <xref:System.Threading.WaitHandle.WaitAny%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cc85-112">To block while waiting for any one of a set of asynchronous operations to complete, store the associated <xref:System.IAsyncResult.AsyncWaitHandle%2A> objects in an array and call one of the <xref:System.Threading.WaitHandle.WaitAny%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cc85-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1cc85-113">Example</span></span>  
 <span data-ttu-id="1cc85-114">В следующем примере кода асинхронные методы класса DNS используются, чтобы получить из службы доменных имен сведения об указанном пользователем компьютере.</span><span class="sxs-lookup"><span data-stu-id="1cc85-114">The following code example demonstrates using asynchronous methods in the DNS class to retrieve Domain Name System information for a user-specified computer.</span></span> <span data-ttu-id="1cc85-115">В этом примере показана блокировка с использованием объекта <xref:System.Threading.WaitHandle>, связанного с асинхронной операцией.</span><span class="sxs-lookup"><span data-stu-id="1cc85-115">The example demonstrates blocking using the <xref:System.Threading.WaitHandle> associated with the asynchronous operation.</span></span> <span data-ttu-id="1cc85-116">Обратите внимание, что в параметрах `null`, `Nothing` и <xref:System.Net.Dns.BeginGetHostByName%2A> передается значение `requestCallback` (`stateObject` в Visual Basic), так как при этом подходе они не являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="1cc85-116">Note that `null` (`Nothing` in Visual Basic) is passed for the <xref:System.Net.Dns.BeginGetHostByName%2A>`requestCallback` and `stateObject` parameters because these are not required when using this approach.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_EndBlockWait.cs#2)]
 [!code-vb[AsyncDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_EndBlockWait.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc85-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1cc85-117">See also</span></span>

- [<span data-ttu-id="1cc85-118">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="1cc85-118">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="1cc85-119">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="1cc85-119">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
