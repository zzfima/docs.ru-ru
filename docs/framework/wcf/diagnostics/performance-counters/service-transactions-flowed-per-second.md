---
title: 'Служба: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: 1151117c8537d4a8eaa4de60d14e314b55ce82d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474848"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="0dc64-102">Служба: количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="0dc64-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="0dc64-103">Имя счетчика: Transactions Flowed Per Second.</span><span class="sxs-lookup"><span data-stu-id="0dc64-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0dc64-104">Описание</span><span class="sxs-lookup"><span data-stu-id="0dc64-104">Description</span></span>  
 <span data-ttu-id="0dc64-105">Количество транзакций в операциях для данной службы в секунду.</span><span class="sxs-lookup"><span data-stu-id="0dc64-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="0dc64-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="0dc64-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0dc64-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0dc64-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
