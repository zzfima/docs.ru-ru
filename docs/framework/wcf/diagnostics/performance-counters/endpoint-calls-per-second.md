---
title: 'Конечная точка: Количество вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: a70df63f6fd268abdd2e1799d1aa38afb41e2811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797219"
---
# <a name="endpoint-calls-per-second"></a>Конечная точка: Количество вызовов в секунду
Имя счетчика: Вызовов в секунду.  
  
## <a name="description"></a>Описание  
 Количество вызовов данной конечной точки в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
