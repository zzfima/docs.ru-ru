---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: a70df63f6fd268abdd2e1799d1aa38afb41e2811
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44059619"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="1a27f-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="1a27f-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="1a27f-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="1a27f-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1a27f-104">Описание</span><span class="sxs-lookup"><span data-stu-id="1a27f-104">Description</span></span>  
 <span data-ttu-id="1a27f-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="1a27f-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="1a27f-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="1a27f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1a27f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1a27f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
