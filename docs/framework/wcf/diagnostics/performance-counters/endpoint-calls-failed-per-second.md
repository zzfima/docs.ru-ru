---
title: 'Конечная точка: Количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100032"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="52066-102">Конечная точка: Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="52066-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="52066-103">Имя счетчика: Количество сбоев вызовов в секунду.</span><span class="sxs-lookup"><span data-stu-id="52066-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="52066-104">Описание</span><span class="sxs-lookup"><span data-stu-id="52066-104">Description</span></span>  
 <span data-ttu-id="52066-105">Количество вызовов, имеющих необработанные исключения и получаемых этой конечной точкой в секунду.</span><span class="sxs-lookup"><span data-stu-id="52066-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="52066-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="52066-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="52066-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="52066-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="52066-108">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="52066-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52066-109">См. также</span><span class="sxs-lookup"><span data-stu-id="52066-109">See also</span></span>

- [<span data-ttu-id="52066-110">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="52066-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
