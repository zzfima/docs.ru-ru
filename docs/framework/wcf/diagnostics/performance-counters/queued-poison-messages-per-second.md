---
title: Количество подозрительных сообщений из очереди в секунду
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916153"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="a38ca-102">Количество подозрительных сообщений из очереди в секунду</span><span class="sxs-lookup"><span data-stu-id="a38ca-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="a38ca-103">Имя счетчика: В очереди подозрительных сообщений в секунду.</span><span class="sxs-lookup"><span data-stu-id="a38ca-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a38ca-104">Описание</span><span class="sxs-lookup"><span data-stu-id="a38ca-104">Description</span></span>  
 <span data-ttu-id="a38ca-105">Количество сообщений, отмеченных как подозрительные транспортом очередей в этой службе в секунду.</span><span class="sxs-lookup"><span data-stu-id="a38ca-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="a38ca-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="a38ca-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a38ca-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a38ca-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
