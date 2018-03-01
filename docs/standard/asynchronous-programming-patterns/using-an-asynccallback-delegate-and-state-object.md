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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb0cdc9e98dcaf3c9f9879359eff0b31c8435773
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="using-an-asynccallback-delegate-and-state-object"></a><span data-ttu-id="4b13f-102">Использование делегата AsyncCallback и объекта состояния</span><span class="sxs-lookup"><span data-stu-id="4b13f-102">Using an AsyncCallback Delegate and State Object</span></span>
<span data-ttu-id="4b13f-103">Если вы используете делегат <xref:System.AsyncCallback>, чтобы обрабатывать результаты асинхронной операции в отдельном потоке, для передачи сведений между обратными вызовами и получения результата можно использовать объект состояния.</span><span class="sxs-lookup"><span data-stu-id="4b13f-103">When you use an <xref:System.AsyncCallback> delegate to process the results of the asynchronous operation in a separate thread, you can use a state object to pass information between the callbacks and to retrieve a final result.</span></span> <span data-ttu-id="4b13f-104">В этой статье для демонстрации этого метода мы дополним пример, приведенный в статье [Использование делегата AsyncCallback для завершения асинхронной операции](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span><span class="sxs-lookup"><span data-stu-id="4b13f-104">This topic demonstrates that practice by expanding the example in [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b13f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="4b13f-105">Example</span></span>  
 <span data-ttu-id="4b13f-106">В следующем примере кода асинхронные методы класса <xref:System.Net.Dns> используются для получения из службы доменных имен (DNS) сведений об указанных пользователем компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4b13f-106">The following code example demonstrates using asynchronous methods in the <xref:System.Net.Dns> class to retrieve Domain Name System (DNS) information for user-specified computers.</span></span> <span data-ttu-id="4b13f-107">В примере определяется и используется класс `HostRequest` для хранения сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="4b13f-107">This example defines and uses the `HostRequest` class to store state information.</span></span> <span data-ttu-id="4b13f-108">Для каждого введенного пользователем имени компьютера создается объект `HostRequest`.</span><span class="sxs-lookup"><span data-stu-id="4b13f-108">A `HostRequest` object gets created for each computer name entered by the user.</span></span> <span data-ttu-id="4b13f-109">Этот объект передается в метод <xref:System.Net.Dns.BeginGetHostByName%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b13f-109">This object is passed to the <xref:System.Net.Dns.BeginGetHostByName%2A> method.</span></span> <span data-ttu-id="4b13f-110">Метод `ProcessDnsInformation` вызывается каждый раз при завершении запроса.</span><span class="sxs-lookup"><span data-stu-id="4b13f-110">The `ProcessDnsInformation` method is called each time a request completes.</span></span> <span data-ttu-id="4b13f-111">Объект `HostRequest` извлекается с помощью свойства <xref:System.IAsyncResult.AsyncState%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b13f-111">The `HostRequest` object is retrieved using the <xref:System.IAsyncResult.AsyncState%2A> property.</span></span> <span data-ttu-id="4b13f-112">Метод `ProcessDnsInformation` использует объект `HostRequest` для сохранения значения <xref:System.Net.IPHostEntry> или исключения <xref:System.Net.Sockets.SocketException>, возвращенных запросом.</span><span class="sxs-lookup"><span data-stu-id="4b13f-112">The `ProcessDnsInformation` method uses the `HostRequest` object to store the <xref:System.Net.IPHostEntry> returned by the request or a <xref:System.Net.Sockets.SocketException> thrown by the request.</span></span> <span data-ttu-id="4b13f-113">Когда все запросы завершаются, приложение выполняет итерацию всех объектов `HostRequest` и выводит сведения о DNS или сообщение об ошибке <xref:System.Net.Sockets.SocketException>.</span><span class="sxs-lookup"><span data-stu-id="4b13f-113">When all requests are complete, the application iterates over the `HostRequest` objects and displays the DNS information or <xref:System.Net.Sockets.SocketException> error message.</span></span>  
  
 [!code-csharp[AsyncDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/AsyncDelegateWithStateObject.cs#5)]
 [!code-vb[AsyncDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/AsyncDelegateWithStateObject.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4b13f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4b13f-114">See Also</span></span>  
 [<span data-ttu-id="4b13f-115">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="4b13f-115">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="4b13f-116">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="4b13f-116">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="4b13f-117">Использование делегата AsyncCallback для завершения асинхронной операции</span><span class="sxs-lookup"><span data-stu-id="4b13f-117">Using an AsyncCallback Delegate to End an Asynchronous Operation</span></span>](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)
