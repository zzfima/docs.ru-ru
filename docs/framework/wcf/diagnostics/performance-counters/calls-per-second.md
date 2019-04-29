---
title: Количество вызовов в секунду
ms.date: 03/30/2017
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
ms.openlocfilehash: 525f3e81c8f574dfd56b69836263472bf23f289f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797362"
---
# <a name="calls-per-second"></a><span data-ttu-id="5b2b5-102">Количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="5b2b5-102">Calls Per Second</span></span>
<span data-ttu-id="5b2b5-103">Имя счетчика: Количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="5b2b5-103">Counter Name: Calls Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5b2b5-104">Описание</span><span class="sxs-lookup"><span data-stu-id="5b2b5-104">Description</span></span>  
 <span data-ttu-id="5b2b5-105">Число вызовов данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="5b2b5-105">Number of calls to this operation in a second.</span></span>  
  
 <span data-ttu-id="5b2b5-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="5b2b5-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5b2b5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5b2b5-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
