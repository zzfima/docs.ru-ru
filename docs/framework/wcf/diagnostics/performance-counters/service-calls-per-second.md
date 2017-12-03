---
title: "Служба: количество вызовов в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a1fd0b3fdbb07a975c23decf0ab389f09033699
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="service-calls-per-second"></a>Служба: количество вызовов в секунду
Имя счетчика: Calls Per Second.  
  
## <a name="description"></a>Описание  
 Количество вызовов данной службы в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F). Здесь числитель (N) - число операций, выполненных за последний интервал измерения, знаменатель (D) - число импульсов, прошедших за последний интервал наблюдения, а F - частота импульсов.
