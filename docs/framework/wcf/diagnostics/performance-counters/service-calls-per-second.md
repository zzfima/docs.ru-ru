---
title: 'Служба: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499891"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="2ea75-102">Служба: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="2ea75-102">Service: Calls Per Second</span></span>
<span data-ttu-id="2ea75-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="2ea75-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2ea75-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2ea75-104">Description</span></span>  
 <span data-ttu-id="2ea75-105">Количество вызовов данной службы в секунду.</span><span class="sxs-lookup"><span data-stu-id="2ea75-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="2ea75-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="2ea75-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2ea75-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Здесь числитель (N) - число операций, выполненных за последний интервал измерения, знаменатель (D) - число импульсов, прошедших за последний интервал наблюдения, а F - частота импульсов.</span><span class="sxs-lookup"><span data-stu-id="2ea75-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
