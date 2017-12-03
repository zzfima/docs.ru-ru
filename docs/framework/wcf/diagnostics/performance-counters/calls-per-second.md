---
title: "Количество вызовов в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: baef18df3e1dda8725859c9529ab61c0668c8ff3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="calls-per-second"></a><span data-ttu-id="98aa8-102">Количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="98aa8-102">Calls Per Second</span></span>
<span data-ttu-id="98aa8-103">Имя счетчика: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="98aa8-103">Counter Name: Calls Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="98aa8-104">Описание</span><span class="sxs-lookup"><span data-stu-id="98aa8-104">Description</span></span>  
 <span data-ttu-id="98aa8-105">Число вызовов данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="98aa8-105">Number of calls to this operation in a second.</span></span>  
  
 <span data-ttu-id="98aa8-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="98aa8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="98aa8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="98aa8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
