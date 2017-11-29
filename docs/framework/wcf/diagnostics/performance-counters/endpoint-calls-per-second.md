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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 559bc945cde67a89d7e0fcdcde3f50e8ff51a138
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="9aee1-102">Конечная точка: количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="9aee1-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="9aee1-103">Имя счетчика: Calls Per Second.</span><span class="sxs-lookup"><span data-stu-id="9aee1-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9aee1-104">Описание</span><span class="sxs-lookup"><span data-stu-id="9aee1-104">Description</span></span>  
 <span data-ttu-id="9aee1-105">Количество вызовов данной конечной точки в секунду.</span><span class="sxs-lookup"><span data-stu-id="9aee1-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="9aee1-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="9aee1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9aee1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9aee1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
