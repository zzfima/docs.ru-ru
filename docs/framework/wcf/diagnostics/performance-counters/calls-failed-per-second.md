---
title: Количество сбоев вызовов в секунду
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: 110ee5c264094f80d5c7c6542c3e388e758e1665
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163167"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="26d11-102">Количество сбоев вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="26d11-102">Calls Failed Per Second</span></span>
<span data-ttu-id="26d11-103">Имя счетчика: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="26d11-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="26d11-104">Описание</span><span class="sxs-lookup"><span data-stu-id="26d11-104">Description</span></span>  
 <span data-ttu-id="26d11-105">Количество вызовов с необработанными исключениями в данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="26d11-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="26d11-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="26d11-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="26d11-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="26d11-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="26d11-108">Этот счетчик увеличивается каждый раз, когда в этой операции имеется необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="26d11-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d11-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="26d11-109">See also</span></span>

- [<span data-ttu-id="26d11-110">Указание и обработка сбоев в контрактах и службах</span><span class="sxs-lookup"><span data-stu-id="26d11-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
