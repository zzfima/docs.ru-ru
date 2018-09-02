---
title: Количество удаленных из очереди сообщений в секунду
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418252"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="06e6d-102">Количество удаленных из очереди сообщений в секунду</span><span class="sxs-lookup"><span data-stu-id="06e6d-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="06e6d-103">Имя счетчика: Queued Messages Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="06e6d-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="06e6d-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="06e6d-104">Description</span></span>  
 <span data-ttu-id="06e6d-105">Количество сообщений, отброшенных транспортом очередей этой службы за секунду.</span><span class="sxs-lookup"><span data-stu-id="06e6d-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="06e6d-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="06e6d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="06e6d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="06e6d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
