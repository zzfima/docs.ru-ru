---
title: "Количество поступивших транзакций в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed6adbaa1f121f11680e0f9574a642565a6f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="c2d34-102">Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="c2d34-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="c2d34-103">Имя счетчика: Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="c2d34-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c2d34-104">Описание</span><span class="sxs-lookup"><span data-stu-id="c2d34-104">Description</span></span>  
 <span data-ttu-id="c2d34-105">Количество транзакций в операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="c2d34-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="c2d34-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="c2d34-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="c2d34-107">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="c2d34-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c2d34-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c2d34-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
