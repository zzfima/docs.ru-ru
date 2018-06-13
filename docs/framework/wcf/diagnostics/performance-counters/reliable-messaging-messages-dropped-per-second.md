---
title: Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 9a87ec509b19f0c566b50ae3672a6c3d2940ee12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474198"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="ef465-102">Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду</span><span class="sxs-lookup"><span data-stu-id="ef465-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="ef465-103">Имя счетчика: Reliable Messaging Sessions Dropped Per Second.</span><span class="sxs-lookup"><span data-stu-id="ef465-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ef465-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ef465-104">Description</span></span>  
 <span data-ttu-id="ef465-105">Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="ef465-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="ef465-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="ef465-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ef465-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ef465-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
