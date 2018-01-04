---
title: "Служба: количество вызовов в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0880ce3674f41367c46f4d0268a5391cfda210ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service-calls-per-second"></a><span data-ttu-id="6af96-102">Служба: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="6af96-102">Service: Calls Per Second</span></span>
<span data-ttu-id="6af96-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="6af96-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6af96-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="6af96-104">Description</span></span>  
 <span data-ttu-id="6af96-105">Количество вызовов данной службы в секунду.</span><span class="sxs-lookup"><span data-stu-id="6af96-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="6af96-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="6af96-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6af96-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Здесь числитель (N) - число операций, выполненных за последний интервал измерения, знаменатель (D) - число импульсов, прошедших за последний интервал наблюдения, а F - частота импульсов.</span><span class="sxs-lookup"><span data-stu-id="6af96-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
