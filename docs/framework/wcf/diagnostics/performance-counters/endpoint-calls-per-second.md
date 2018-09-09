---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: a70df63f6fd268abdd2e1799d1aa38afb41e2811
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249027"
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="137dc-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="137dc-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="137dc-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="137dc-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="137dc-104">Описание</span><span class="sxs-lookup"><span data-stu-id="137dc-104">Description</span></span>  
 <span data-ttu-id="137dc-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="137dc-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="137dc-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="137dc-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="137dc-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="137dc-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
