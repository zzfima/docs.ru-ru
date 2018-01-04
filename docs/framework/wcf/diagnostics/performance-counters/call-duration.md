---
title: "Длительность обработки вызова"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4973ec3-3c66-4c0b-b5d0-294b62c83f7d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a306be97f1fd1b630fd59c1a154c08b3f1189c8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="call-duration"></a><span data-ttu-id="fc325-102">Длительность обработки вызова</span><span class="sxs-lookup"><span data-stu-id="fc325-102">Call Duration</span></span>
<span data-ttu-id="fc325-103">Имя счетчика: Call Duration</span><span class="sxs-lookup"><span data-stu-id="fc325-103">Counter Name: Call Duration</span></span>  
  
## <a name="description"></a><span data-ttu-id="fc325-104">Описание</span><span class="sxs-lookup"><span data-stu-id="fc325-104">Description</span></span>  
 <span data-ttu-id="fc325-105">Средняя длительность вызовов этой операции.</span><span class="sxs-lookup"><span data-stu-id="fc325-105">The average duration of calls to this operation.</span></span> <span data-ttu-id="fc325-106">Средняя длительность вычисляется по следующей формуле: (N1-N0)/(D1-D0).</span><span class="sxs-lookup"><span data-stu-id="fc325-106">The average duration is calculated based on this equation: (N1-N0)/(D1-D0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fc325-107">При использовании в асинхронной службе WCF счетчик Call Duration всегда возвращает -1.</span><span class="sxs-lookup"><span data-stu-id="fc325-107">When used on an asynchronous WCF service the Call Duration counter will always return -1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc325-108">См. также</span><span class="sxs-lookup"><span data-stu-id="fc325-108">See Also</span></span>  
 [<span data-ttu-id="fc325-109">PERF_AVERAGE_TIMER</span><span class="sxs-lookup"><span data-stu-id="fc325-109">PERF_AVERAGE_TIMER</span></span>](http://go.microsoft.com/fwlink/?LinkId=95015)
