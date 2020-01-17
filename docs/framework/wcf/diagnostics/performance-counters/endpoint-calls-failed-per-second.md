---
title: 'Конечная точка: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 25e504221097505e622a3ba60f0c7e85ec455f36
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163622"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="12a84-102">Конечная точка: количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="12a84-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="12a84-103">Имя счетчика: Calls Failed Per Second.</span><span class="sxs-lookup"><span data-stu-id="12a84-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="12a84-104">Описание</span><span class="sxs-lookup"><span data-stu-id="12a84-104">Description</span></span>  
 <span data-ttu-id="12a84-105">Количество вызовов, имеющих необработанные исключения и получаемых этой конечной точкой в секунду.</span><span class="sxs-lookup"><span data-stu-id="12a84-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="12a84-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="12a84-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="12a84-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="12a84-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="12a84-108">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="12a84-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a84-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="12a84-109">See also</span></span>

- [<span data-ttu-id="12a84-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="12a84-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
