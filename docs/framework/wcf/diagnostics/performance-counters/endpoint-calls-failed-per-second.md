---
title: 'Конечная точка: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 9634f8a170bb2fae2f15c3f00dcabb95d512c74e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321462"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="08339-102">Конечная точка: количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="08339-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="08339-103">Имя счетчика: Calls Failed Per Second.</span><span class="sxs-lookup"><span data-stu-id="08339-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08339-104">Описание</span><span class="sxs-lookup"><span data-stu-id="08339-104">Description</span></span>  
 <span data-ttu-id="08339-105">Количество вызовов, имеющих необработанные исключения и получаемых этой конечной точкой в секунду.</span><span class="sxs-lookup"><span data-stu-id="08339-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="08339-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="08339-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="08339-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="08339-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="08339-108">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="08339-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08339-109">См. также</span><span class="sxs-lookup"><span data-stu-id="08339-109">See also</span></span>

- [<span data-ttu-id="08339-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="08339-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
