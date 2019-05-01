---
title: Количество прерванных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998196"
---
# <a name="transacted-operations-aborted-per-second"></a><span data-ttu-id="fd67e-102">Количество прерванных операций с поддержкой транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="fd67e-102">Transacted Operations Aborted Per Second</span></span>
<span data-ttu-id="fd67e-103">Имя счетчика: Количество прерванных операций в секунду.</span><span class="sxs-lookup"><span data-stu-id="fd67e-103">Counter Name: Transacted Operations Aborted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fd67e-104">Описание</span><span class="sxs-lookup"><span data-stu-id="fd67e-104">Description</span></span>  
 <span data-ttu-id="fd67e-105">Количество транзакционных операций, прерванных в этой службе за секунду.</span><span class="sxs-lookup"><span data-stu-id="fd67e-105">Number of transactional operations that have been aborted in this service in a second.</span></span>  
  
 <span data-ttu-id="fd67e-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="fd67e-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fd67e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="fd67e-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
