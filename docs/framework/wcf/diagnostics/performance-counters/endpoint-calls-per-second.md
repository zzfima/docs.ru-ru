---
title: 'Конечная точка: количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: a70df63f6fd268abdd2e1799d1aa38afb41e2811
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43804621"
---
# <a name="endpoint-calls-per-second"></a>Конечная точка: количество вызовов в секунду
Имя счетчика: Calls Per Second.  
  
## <a name="description"></a>Описание  
 Количество вызовов данной конечной точки в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
