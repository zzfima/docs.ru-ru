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
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="1e743-102">Использование делегата AsyncCallback для завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="1e743-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="1e743-103">Приложения, которые могут выполнять другую работу во время ожидания результатов асинхронной операции не должны блокировать ожидание до завершения операции.</span><span class="sxs-lookup"><span data-stu-id="1e743-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="1e743-104">Для продолжения выполнения инструкций при ожидании завершения асинхронной операции, используйте один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="1e743-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="1e743-105">Используйте <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="1e743-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="1e743-106">Этот подход демонстрируется в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="1e743-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="1e743-107">Используйте <xref:System.IAsyncResult.IsCompleted%2A> свойство <xref:System.IAsyncResult> возвращенные асинхронной операцией **начать** *Имя_операции* метод, чтобы определить, завершена ли операция.</span><span class="sxs-lookup"><span data-stu-id="1e743-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin** *OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="1e743-108">Пример, демонстрирующий этот способ см. в разделе [запрос состояния асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="1e743-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e743-109">Пример</span><span class="sxs-lookup"><span data-stu-id="1e743-109">Example</span></span>  
 <span data-ttu-id="1e743-110">В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен (DNS) для указанных пользователем компьютеров.</span><span class="sxs-lookup"><span data-stu-id="1e743-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="1e743-111">В этом примере создается <xref:System.AsyncCallback> делегат, который ссылается `ProcessDnsInformation` метод.</span><span class="sxs-lookup"><span data-stu-id="1e743-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="1e743-112">Этот метод вызывается один раз для каждого асинхронного запроса сведений DNS.</span><span class="sxs-lookup"><span data-stu-id="1e743-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="1e743-113">Обратите внимание, что передаваемый узла определяемый пользователем <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.Object> параметра.</span><span class="sxs-lookup"><span data-stu-id="1e743-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="1e743-114">Пример, демонстрирующий определения и использования более сложного объекта состояния см. в разделе [использование делегата AsyncCallback и объект состояния](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="1e743-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="1e743-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1e743-115">See Also</span></span>  
 [<span data-ttu-id="1e743-116">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="1e743-116">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="1e743-117">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="1e743-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="1e743-118">Вызов асинхронных методов с помощью IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="1e743-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="1e743-119">Использование делегата AsyncCallback и объекта состояния</span><span class="sxs-lookup"><span data-stu-id="1e743-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
