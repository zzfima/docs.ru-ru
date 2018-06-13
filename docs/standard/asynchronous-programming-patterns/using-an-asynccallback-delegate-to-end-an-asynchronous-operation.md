---
title: Использование делегата AsyncCallback для завершения асинхронной операции
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ending asynchronous operations
- asynchronous programming, ending operations
- AsyncCallback delegate
- stopping asynchronous operations
ms.assetid: 9d97206c-8917-406c-8961-7d0909d84eeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e67cd0fca1532aa2f52aeb7d34f604c1feb0723e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567410"
---
# <a name="using-an-asynccallback-delegate-to-end-an-asynchronous-operation"></a><span data-ttu-id="db342-102">Использование делегата AsyncCallback для завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="db342-102">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>
<span data-ttu-id="db342-103">Приложения, которые могут выполнять работу во время ожидания результатов асинхронной операции, не должны блокироваться до завершения этой операции.</span><span class="sxs-lookup"><span data-stu-id="db342-103">Applications that can do other work while waiting for the results of an asynchronous operation should not block waiting until the operation completes.</span></span> <span data-ttu-id="db342-104">Используйте один из следующих вариантов, чтобы продолжить выполнение инструкций в период ожидания асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="db342-104">Use one of the following options to continue executing instructions while waiting for an asynchronous operation to complete:</span></span>  
  
-   <span data-ttu-id="db342-105">Используйте делегата <xref:System.AsyncCallback> для обработки результатов асинхронной операции в отдельном потоке.</span><span class="sxs-lookup"><span data-stu-id="db342-105">Use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread.</span></span> <span data-ttu-id="db342-106">Именно этот подход демонстрируется в этой статье.</span><span class="sxs-lookup"><span data-stu-id="db342-106">This approach is demonstrated in this topic.</span></span>  
  
-   <span data-ttu-id="db342-107">Чтобы определить, завершена ли операция, используется свойство <xref:System.IAsyncResult.IsCompleted%2A> объекта <xref:System.IAsyncResult>, возвращаемого методом **Begin***Имя_операции* асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="db342-107">Use the <xref:System.IAsyncResult.IsCompleted%2A> property of the <xref:System.IAsyncResult> returned by the asynchronous operation's **Begin***OperationName* method to determine whether the operation has completed.</span></span> <span data-ttu-id="db342-108">Пример, демонстрирующий этот подход, см. в разделе [Запрос состояния асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="db342-108">For an example that demonstrates this approach, see [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db342-109">Пример</span><span class="sxs-lookup"><span data-stu-id="db342-109">Example</span></span>  
 <span data-ttu-id="db342-110">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются для получения из службы доменных имен (DNS) сведений об указанных пользователем компьютерах.</span><span class="sxs-lookup"><span data-stu-id="db342-110">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="db342-111">Этот пример создает делегат <xref:System.AsyncCallback>, который ссылается на метод `ProcessDnsInformation`.</span><span class="sxs-lookup"><span data-stu-id="db342-111">This example creates an <xref:System.AsyncCallback> delegate that references the `ProcessDnsInformation` method.</span></span> <span data-ttu-id="db342-112">Этот метод вызывается один раз для каждого асинхронного запроса сведений DNS.</span><span class="sxs-lookup"><span data-stu-id="db342-112">This method is called once for each asynchronous request for DNS information.</span></span>  
  
 <span data-ttu-id="db342-113">Обратите внимание, что в параметре <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> передается узел, указанный пользователем.</span><span class="sxs-lookup"><span data-stu-id="db342-113">Note that the user-specified host is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A><xref:System.Object> parameter.</span></span> <span data-ttu-id="db342-114">Пример, демонстрирующий определения и использования более сложного объекта состояния, представлен в статье [Использование делегата AsyncCallback и объекта состояния](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span><span class="sxs-lookup"><span data-stu-id="db342-114">For an example that demonstrates defining and using a more complex state object, see [Using an AsyncCallback Delegate and State Object](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md).</span></span>  
  
 [!code-csharp[AsyncDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateNoStateObject.cs#4)]
 [!code-vb[AsyncDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateNoState.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="db342-115">См. также</span><span class="sxs-lookup"><span data-stu-id="db342-115">See Also</span></span>  
 [<span data-ttu-id="db342-116">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="db342-116">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="db342-117">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="db342-117">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="db342-118">Вызов асинхронных методов с помощью IAsyncResult</span><span class="sxs-lookup"><span data-stu-id="db342-118">Calling Asynchronous Methods Using IAsyncResult</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-asynchronous-methods-using-iasyncresult.md)  
 [<span data-ttu-id="db342-119">Использование делегата AsyncCallback и объекта состояния</span><span class="sxs-lookup"><span data-stu-id="db342-119">Using an AsyncCallback Delegate and State Object</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
