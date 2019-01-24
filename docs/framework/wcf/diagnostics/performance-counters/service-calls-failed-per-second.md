---
title: 'Служба: Количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: a043cf30fa67707aca3edf50cf23372ade5e5a42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559896"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="8ae60-102">Служба: Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="8ae60-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="8ae60-103">Имя счетчика: Количество сбоев вызовов в секунду.</span><span class="sxs-lookup"><span data-stu-id="8ae60-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ae60-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="8ae60-104">Description</span></span>  
 <span data-ttu-id="8ae60-105">Число вызовов с необработанными исключениями, получаемых этой службой за секунду.</span><span class="sxs-lookup"><span data-stu-id="8ae60-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="8ae60-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="8ae60-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8ae60-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8ae60-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="8ae60-108">В управляемом коде исключения создаются в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="8ae60-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="8ae60-109">В управляемом коде исключения создаются в случае возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="8ae60-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="8ae60-110">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.</span><span class="sxs-lookup"><span data-stu-id="8ae60-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae60-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8ae60-111">See also</span></span>
- [<span data-ttu-id="8ae60-112">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="8ae60-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
