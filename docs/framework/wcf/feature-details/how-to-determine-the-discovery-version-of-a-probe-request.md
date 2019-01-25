---
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 356ddd76bdee0698fa446d830791f702af5742b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595127"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="a636b-102">Как определить версию обнаружения зондирующего запроса</span><span class="sxs-lookup"><span data-stu-id="a636b-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="a636b-103">Прокси-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a636b-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="a636b-104">При поступлении на прокси-сервер многоадресного зондирующего запроса UDP прокси-сервер должен ответить многоадресным сообщением отмены.</span><span class="sxs-lookup"><span data-stu-id="a636b-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="a636b-105">Чтобы сделать это, ему требуется знать версию обнаружения запроса.</span><span class="sxs-lookup"><span data-stu-id="a636b-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="a636b-106">Определение версии обнаружения зондирующего запроса</span><span class="sxs-lookup"><span data-stu-id="a636b-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="a636b-107">В методе, который отвечает на зондирующий запрос (например, <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>), используйте статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A>, чтобы выполнить поиск <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="a636b-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a636b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="a636b-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="a636b-109">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="a636b-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
