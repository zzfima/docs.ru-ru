---
title: Счетчики производительности конечных точек
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: de750b3e5ee61b6bfc5b387fb7de84b74171d8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501965"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="d2d03-102">Счетчики производительности конечных точек</span><span class="sxs-lookup"><span data-stu-id="d2d03-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="d2d03-103">Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения.</span><span class="sxs-lookup"><span data-stu-id="d2d03-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="d2d03-104">Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="d2d03-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="d2d03-105">Экземплярам присваиваются имена согласно следующему шаблону:</span><span class="sxs-lookup"><span data-stu-id="d2d03-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="d2d03-106">Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.</span><span class="sxs-lookup"><span data-stu-id="d2d03-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d2d03-107">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="d2d03-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="d2d03-108">Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.</span><span class="sxs-lookup"><span data-stu-id="d2d03-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2d03-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d2d03-109">See also</span></span>
- [<span data-ttu-id="d2d03-110">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="d2d03-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
