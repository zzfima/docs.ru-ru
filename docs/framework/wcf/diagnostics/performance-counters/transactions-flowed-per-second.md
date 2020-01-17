---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: 8b6077af3f98f7a205772b4883dc122374083e00
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163830"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="1f6a2-102">Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="1f6a2-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="1f6a2-103">Имя счетчика: Количество поступивших транзакций в секунду</span><span class="sxs-lookup"><span data-stu-id="1f6a2-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f6a2-104">Описание</span><span class="sxs-lookup"><span data-stu-id="1f6a2-104">Description</span></span>  
 <span data-ttu-id="1f6a2-105">Количество транзакций в операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="1f6a2-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="1f6a2-106">Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.</span><span class="sxs-lookup"><span data-stu-id="1f6a2-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="1f6a2-107">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="1f6a2-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1f6a2-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1f6a2-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
