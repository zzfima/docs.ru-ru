---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: ff9320b0990a0543bbb1da553d040ff5a4b4fed9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178624"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="07f3a-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="07f3a-102">Calls Failed Per Second</span></span>
<span data-ttu-id="07f3a-103">Имя счетчика: Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="07f3a-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="07f3a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="07f3a-104">Description</span></span>  
 <span data-ttu-id="07f3a-105">Количество вызовов с необработанными исключениями в данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="07f3a-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="07f3a-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="07f3a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="07f3a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="07f3a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="07f3a-108">Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной операции.</span><span class="sxs-lookup"><span data-stu-id="07f3a-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f3a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="07f3a-109">See also</span></span>

- [<span data-ttu-id="07f3a-110">Задание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="07f3a-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
