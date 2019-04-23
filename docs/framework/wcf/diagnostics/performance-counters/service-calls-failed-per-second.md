---
title: 'Служба: Количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: d87d5f06d0c9a3849ec80a3d1c7badefde7cf372
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167496"
---
# <a name="service-calls-failed-per-second"></a>Служба: Количество сбоев вызовов в секунду
Имя счетчика: Количество сбоев вызовов в секунду.  
  
## <a name="description"></a>Описание  
 Число вызовов с необработанными исключениями, получаемых этой службой за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 В управляемом коде исключения создаются в случае возникновения ошибки.  
  
 Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной службе.  
  
## <a name="see-also"></a>См. также

- [Указание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
