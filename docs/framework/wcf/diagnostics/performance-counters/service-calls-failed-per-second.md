---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 6af8f79d1fe163967a5c6e8220697aa11bee66c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="service-calls-failed-per-second"></a>Служба: количество сбоев вызовов в секунду
Имя счетчика: Calls Failed Per Second.  
  
## <a name="description"></a>Описание  
 Число вызовов с необработанными исключениями, получаемых этой службой за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.  
  
## <a name="see-also"></a>См. также  
 [Указание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
