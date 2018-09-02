---
title: Количество прерванных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417486"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="04eb8-102">Количество прерванных операций с поддержкой транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="04eb8-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="04eb8-103">Имя счетчика: Количество прерванных операций с поддержкой транзакций в секунду.</span><span class="sxs-lookup"><span data-stu-id="04eb8-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="04eb8-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="04eb8-104">Description</span></span>  
 <span data-ttu-id="04eb8-105">Количество транзакционных операций, прерванных в этой службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="04eb8-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="04eb8-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="04eb8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="04eb8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="04eb8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
