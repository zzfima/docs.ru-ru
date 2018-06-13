---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 186d59d2f0255f0f964130659a2053fc8f440dd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474510"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="3cf95-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="3cf95-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="3cf95-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="3cf95-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3cf95-104">Описание</span><span class="sxs-lookup"><span data-stu-id="3cf95-104">Description</span></span>  
 <span data-ttu-id="3cf95-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="3cf95-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="3cf95-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="3cf95-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3cf95-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3cf95-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
