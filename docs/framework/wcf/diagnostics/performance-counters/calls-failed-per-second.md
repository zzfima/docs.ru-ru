---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: bad37e0124698209955603c1b7d8a1aec4b87418
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521053"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="c5f9e-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="c5f9e-102">Calls Failed Per Second</span></span>
<span data-ttu-id="c5f9e-103">Имя счетчика: Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="c5f9e-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="c5f9e-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5f9e-104">Description</span></span>  
 <span data-ttu-id="c5f9e-105">Количество вызовов с необработанными исключениями в данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="c5f9e-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="c5f9e-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="c5f9e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c5f9e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c5f9e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="c5f9e-108">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной операции.</span><span class="sxs-lookup"><span data-stu-id="c5f9e-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f9e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f9e-109">See also</span></span>
- [<span data-ttu-id="c5f9e-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="c5f9e-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
