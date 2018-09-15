---
title: Количество операций с поддержкой транзакций с сомнительным результатом в секунду
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: f7365c4e5f03711129916c8c6964f7e25e9b553e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45638007"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="e8d93-102">Количество операций с поддержкой транзакций с сомнительным результатом в секунду</span><span class="sxs-lookup"><span data-stu-id="e8d93-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="e8d93-103">Имя счетчика: Количество операций с поддержкой транзакций с сомнительным результатом в секунду.</span><span class="sxs-lookup"><span data-stu-id="e8d93-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e8d93-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e8d93-104">Description</span></span>  
 <span data-ttu-id="e8d93-105">Количество операций с поддержкой транзакций, имеющих сомнительный результат, возникающих в данной службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="e8d93-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="e8d93-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="e8d93-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="e8d93-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="e8d93-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
