---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: a71095b9fdd16d7e220be8a0aeb0a746bb50527e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="914e9-102">Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="914e9-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="914e9-103">Имя счетчика: Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="914e9-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="914e9-104">Описание</span><span class="sxs-lookup"><span data-stu-id="914e9-104">Description</span></span>  
 <span data-ttu-id="914e9-105">Количество транзакций в операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="914e9-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="914e9-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="914e9-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="914e9-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="914e9-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="914e9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="914e9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
