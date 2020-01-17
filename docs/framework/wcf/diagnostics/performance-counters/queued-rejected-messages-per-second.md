---
title: Количество сообщений из очереди, отклоненных за секунду
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 805b4f5d1e7882f38cfcc76ad63451d735389d5f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163973"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="3640a-102">Количество сообщений из очереди, отклоненных за секунду</span><span class="sxs-lookup"><span data-stu-id="3640a-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="3640a-103">Имя счетчика: Queued Messages Rejected Per Second.</span><span class="sxs-lookup"><span data-stu-id="3640a-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3640a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="3640a-104">Description</span></span>  
 <span data-ttu-id="3640a-105">Количество сообщений, отклоненных транспортом очередей этой службы за секунду.</span><span class="sxs-lookup"><span data-stu-id="3640a-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="3640a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span><span class="sxs-lookup"><span data-stu-id="3640a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="3640a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="3640a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
