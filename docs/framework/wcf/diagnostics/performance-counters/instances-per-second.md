---
title: Количество экземпляров в секунду
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: f0797c38a5eb7399817eaf6aad9fb5b6ecbfab89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916502"
---
# <a name="instances-per-second"></a><span data-ttu-id="01aa3-102">Количество экземпляров в секунду</span><span class="sxs-lookup"><span data-stu-id="01aa3-102">Instances Per Second</span></span>
<span data-ttu-id="01aa3-103">Имя счетчика: Экземпляры, создаваемых в секунду.</span><span class="sxs-lookup"><span data-stu-id="01aa3-103">Counter Name: Instances Created Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="01aa3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="01aa3-104">Description</span></span>  
 <span data-ttu-id="01aa3-105">Общее количество экземпляров службы, создаваемых за секунду.</span><span class="sxs-lookup"><span data-stu-id="01aa3-105">Total number of service instances created in a second.</span></span>  
  
 <span data-ttu-id="01aa3-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="01aa3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="01aa3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="01aa3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
