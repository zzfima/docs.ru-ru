---
title: 'Конечная точка: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 39458dcb6ac033fd5084b5f2e760e0e26c345da7
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163557"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="918ed-102">Конечная точка: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="918ed-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="918ed-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="918ed-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="918ed-104">Описание</span><span class="sxs-lookup"><span data-stu-id="918ed-104">Description</span></span>  
 <span data-ttu-id="918ed-105">Количество транзакций, поступивших в операции в этой конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="918ed-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="918ed-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="918ed-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="918ed-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="918ed-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="918ed-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="918ed-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
