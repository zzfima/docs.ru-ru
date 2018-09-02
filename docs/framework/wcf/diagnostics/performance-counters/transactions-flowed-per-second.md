---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392940"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="41436-102">Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="41436-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="41436-103">Имя счетчика: Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="41436-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="41436-104">Описание</span><span class="sxs-lookup"><span data-stu-id="41436-104">Description</span></span>  
 <span data-ttu-id="41436-105">Количество транзакций в операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="41436-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="41436-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="41436-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="41436-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="41436-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="41436-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="41436-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
