---
title: 'Служба: количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 9cd649788e1304c68caa1bbf4b5fd27e6fc9d508
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559068"
---
# <a name="service-calls-failed-per-second"></a>Служба: количество сбоев вызовов в секунду
Имя счетчика: Calls Failed Per Second.  
  
## <a name="description"></a>Описание  
 Число вызовов с необработанными исключениями, получаемых этой службой за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.  
  
## <a name="see-also"></a>См. также  
 [Указание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
