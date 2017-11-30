---
title: "Использование делегата AsyncCallback и объекта состояния"
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
- asynchronous programming, delegates
- AsyncCallback delegate, samples
- asynchronous programming, state objects
- IAsyncResult interface, samples
ms.assetid: e3e5475d-c5e9-43f0-928e-d18df8ca1f1d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e8793a78289e9b58407038f41cc9d403ff9f9940
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="3ba1e-102">Использование делегата AsyncCallback и объекта состояния</span><span class="sxs-lookup"><span data-stu-id="3ba1e-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="3ba1e-103">При использовании <xref:System.AsyncCallback> делегата для обработки результатов асинхронной операции в отдельном потоке, объект состояния можно использовать для передачи сведений между обратных вызовов и для получения окончательного результата.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="3ba1e-104">В этом разделе демонстрируется такой подход, развернув в примере в [использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="3ba1e-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ba1e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3ba1e-105">Example</span></span>  
 <span data-ttu-id="3ba1e-106">В следующем примере кода показано использование асинхронных методов в <xref:System.Net.Dns> класс, чтобы получить сведения о системе доменных имен (DNS) для указанных пользователем компьютеров.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="3ba1e-107">В этом примере определяется и используется `HostRequest` класса для хранения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="3ba1e-108">Объект `HostRequest` создается для каждого введенного пользователем имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="3ba1e-109">Этот объект передается <xref:System.Net.Dns.BeginGetHostByName%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="3ba1e-110">`ProcessDnsInformation` Метод вызывается каждый раз при завершении запроса.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="3ba1e-111">`HostRequest` Объект извлекается с помощью <xref:System.IAsyncResult.AsyncState%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="3ba1e-112">`ProcessDnsInformation` Использует метод `HostRequest` объект для хранения <xref:System.Net.IPHostEntry> возвращаемых по запросу или <xref:System.Net.Sockets.SocketException> выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="3ba1e-113">После выполнения всех запросов приложение выполняет итерацию `HostRequest` объектов и отображает сведения о DNS или <xref:System.Net.Sockets.SocketException> сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3ba1e-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="3ba1e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3ba1e-114">See Also</span></span>  
 [<span data-ttu-id="3ba1e-115">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="3ba1e-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="3ba1e-116">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="3ba1e-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="3ba1e-117">Использование делегата AsyncCallback для завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="3ba1e-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
