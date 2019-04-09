---
title: Счетчики производительности конечных точек
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: f07e318e39a68e689ec484b09fa743623cfb51d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158396"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="56463-102">Счетчики производительности конечных точек</span><span class="sxs-lookup"><span data-stu-id="56463-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="56463-103">Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения.</span><span class="sxs-lookup"><span data-stu-id="56463-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="56463-104">Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="56463-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="56463-105">Экземплярам присваиваются имена согласно следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="56463-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="56463-106">Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="56463-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="56463-107">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="56463-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="56463-108">Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.</span><span class="sxs-lookup"><span data-stu-id="56463-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56463-109">См. также</span><span class="sxs-lookup"><span data-stu-id="56463-109">See also</span></span>

- [<span data-ttu-id="56463-110">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="56463-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
