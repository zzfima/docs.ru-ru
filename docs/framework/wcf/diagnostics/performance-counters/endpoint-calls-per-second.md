---
title: "Конечная точка: количество вызовов в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 480e0758df7e3062f9bd2b0b089c7a9b75e1c012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="58d03-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="58d03-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="58d03-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="58d03-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="58d03-104">Описание</span><span class="sxs-lookup"><span data-stu-id="58d03-104">Description</span></span>  
 <span data-ttu-id="58d03-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="58d03-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="58d03-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="58d03-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="58d03-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="58d03-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
