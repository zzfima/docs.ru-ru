---
title: Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: fafc63d692d2a6892330b0be5fe534ace5d7f0ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473208"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="4cd26-102">Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду</span><span class="sxs-lookup"><span data-stu-id="4cd26-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="4cd26-103">Имя счетчика: Reliable Messaging Sessions Faulted Per Second.</span><span class="sxs-lookup"><span data-stu-id="4cd26-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4cd26-104">Описание</span><span class="sxs-lookup"><span data-stu-id="4cd26-104">Description</span></span>  
 <span data-ttu-id="4cd26-105">Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.</span><span class="sxs-lookup"><span data-stu-id="4cd26-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="4cd26-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="4cd26-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="4cd26-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="4cd26-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
