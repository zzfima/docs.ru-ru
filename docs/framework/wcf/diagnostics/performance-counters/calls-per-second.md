---
title: Количество вызовов в секунду
ms.date: 03/30/2017
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
ms.openlocfilehash: 94d499d70445bc9c162d9f6ee9aadb3a025c744f
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163583"
---
# <a name="calls-per-second"></a><span data-ttu-id="6838a-102">Количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="6838a-102">Calls Per Second</span></span>
<span data-ttu-id="6838a-103">Имя счетчика: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="6838a-103">Counter Name: Calls Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="6838a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="6838a-104">Description</span></span>  
 <span data-ttu-id="6838a-105">Число вызовов данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="6838a-105">Number of calls to this operation in a second.</span></span>  
  
 <span data-ttu-id="6838a-106">Этот счетчик имеет тип счетчика производительности [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), значение которого вычисляется с помощью следующей формулы.</span><span class="sxs-lookup"><span data-stu-id="6838a-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6838a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6838a-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
