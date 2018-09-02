---
title: 'Конечная точка: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405015"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="cf633-102">Конечная точка: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="cf633-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="cf633-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="cf633-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cf633-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="cf633-104">Description</span></span>  
 <span data-ttu-id="cf633-105">Количество транзакций, поступивших в операции в этой конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="cf633-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="cf633-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="cf633-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="cf633-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="cf633-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="cf633-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="cf633-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
