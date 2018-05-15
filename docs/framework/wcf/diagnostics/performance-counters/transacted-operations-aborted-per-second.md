---
title: Количество прерванных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: dacdf93f4610df9161134a41ece19fd2a18637c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="97e2a-102">Количество прерванных операций с поддержкой транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="97e2a-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="97e2a-103">Имя счетчика: Количество прерванных операций с поддержкой транзакций в секунду.</span><span class="sxs-lookup"><span data-stu-id="97e2a-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="97e2a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="97e2a-104">Description</span></span>  
 <span data-ttu-id="97e2a-105">Количество транзакционных операций, прерванных в этой службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="97e2a-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="97e2a-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="97e2a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="97e2a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="97e2a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
