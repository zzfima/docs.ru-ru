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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54e8b60679c7e7106f5b2e28abfebe5adc589174
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="calls-per-second"></a><span data-ttu-id="994d0-102">Количество вызовов в секунду</span><span class="sxs-lookup"><span data-stu-id="994d0-102">Calls Per Second</span></span>
<span data-ttu-id="994d0-103">Имя счетчика: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="994d0-103">Counter Name: Calls Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="994d0-104">Описание</span><span class="sxs-lookup"><span data-stu-id="994d0-104">Description</span></span>  
 <span data-ttu-id="994d0-105">Число вызовов данной операции в секунду.</span><span class="sxs-lookup"><span data-stu-id="994d0-105">Number of calls to this operation in a second.</span></span>  
  
 <span data-ttu-id="994d0-106">Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.</span><span class="sxs-lookup"><span data-stu-id="994d0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="994d0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="994d0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
