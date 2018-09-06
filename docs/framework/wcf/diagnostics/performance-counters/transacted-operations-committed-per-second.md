---
title: Количество зафиксированных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856326"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="223f7-102">Количество зафиксированных операций с поддержкой транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="223f7-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="223f7-103">Имя счетчика: Количество зафиксированных операций с поддержкой транзакций в секунду.</span><span class="sxs-lookup"><span data-stu-id="223f7-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="223f7-104">Описание</span><span class="sxs-lookup"><span data-stu-id="223f7-104">Description</span></span>  
 <span data-ttu-id="223f7-105">Количество транзакционных операций, зафиксированных в этой службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="223f7-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="223f7-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="223f7-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="223f7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="223f7-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
