---
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425266"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="769aa-102">Как определить версию обнаружения зондирующего запроса</span><span class="sxs-lookup"><span data-stu-id="769aa-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="769aa-103">Прокси-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения.</span><span class="sxs-lookup"><span data-stu-id="769aa-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="769aa-104">При многоадресной рассылки UDP Зондирующий запрос прибывает в прокси-сервер, прокси-сервер должен вернуть ответ с многоадресное сообщение отмены.</span><span class="sxs-lookup"><span data-stu-id="769aa-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="769aa-105">Чтобы сделать это, необходимо знать версию обнаружения запроса.</span><span class="sxs-lookup"><span data-stu-id="769aa-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="769aa-106">Определение версии обнаружения зондирующего запроса</span><span class="sxs-lookup"><span data-stu-id="769aa-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="769aa-107">В методе, который отвечает на Зондирующий запрос (например <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) используйте статический <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> искомое свойство <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="769aa-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="769aa-108">См. также</span><span class="sxs-lookup"><span data-stu-id="769aa-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="769aa-109">Реализация прокси-сервера обнаружения</span><span class="sxs-lookup"><span data-stu-id="769aa-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
