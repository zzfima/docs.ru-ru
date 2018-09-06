---
title: 'Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863508"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="4a2a6-102">Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="4a2a6-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="4a2a6-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="4a2a6-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4a2a6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="4a2a6-104">Description</span></span>  
 <span data-ttu-id="4a2a6-105">Общее количество сообщений системы надежного обмена сообщениями, которое было отброшено в данной конечной точке в секунду.</span><span class="sxs-lookup"><span data-stu-id="4a2a6-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="4a2a6-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="4a2a6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4a2a6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="4a2a6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
