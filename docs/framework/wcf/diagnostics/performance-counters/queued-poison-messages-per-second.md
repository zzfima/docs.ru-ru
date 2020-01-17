---
title: Количество подозрительных сообщений из очереди в секунду
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d755b9c9e4c8e7ef9e57a0d93c05f87830d63c5c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163999"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="7942a-102">Количество подозрительных сообщений из очереди в секунду</span><span class="sxs-lookup"><span data-stu-id="7942a-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="7942a-103">Имя счетчика: Queued Poison Messages Per Second.</span><span class="sxs-lookup"><span data-stu-id="7942a-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="7942a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="7942a-104">Description</span></span>  
 <span data-ttu-id="7942a-105">Количество сообщений, отмеченных как подозрительные транспортом очередей в этой службе в секунду.</span><span class="sxs-lookup"><span data-stu-id="7942a-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="7942a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span><span class="sxs-lookup"><span data-stu-id="7942a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="7942a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="7942a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
