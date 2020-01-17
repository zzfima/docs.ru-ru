---
title: 'Служба: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: be5d77169a71d6f44205a1150da5239eceff7d9c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163908"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="5694d-102">Служба: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="5694d-102">Service: Calls Per Second</span></span>
<span data-ttu-id="5694d-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="5694d-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5694d-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5694d-104">Description</span></span>  
 <span data-ttu-id="5694d-105">Количество вызовов данной службы в секунду.</span><span class="sxs-lookup"><span data-stu-id="5694d-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="5694d-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="5694d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5694d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Здесь числитель (N) - число операций, выполненных за последний интервал измерения, знаменатель (D) - число импульсов, прошедших за последний интервал наблюдения, а F - частота импульсов.</span><span class="sxs-lookup"><span data-stu-id="5694d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
