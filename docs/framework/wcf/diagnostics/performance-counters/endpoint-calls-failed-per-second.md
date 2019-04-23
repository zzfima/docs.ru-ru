---
title: 'Конечная точка: Количество сбоев вызовов в секунду'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 52419f45adde768d19d6b46642d52ad0a1844197
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100032"
---
# <a name="endpoint-calls-failed-per-second"></a>Конечная точка: Количество сбоев вызовов в секунду
Имя счетчика: Количество сбоев вызовов в секунду.  
  
## <a name="description"></a>Описание  
 Количество вызовов, имеющих необработанные исключения и получаемых этой конечной точкой в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 Значение этого счетчика увеличивается при каждом обнаружении необработанного исключения в данной конечной точке.  
  
## <a name="see-also"></a>См. также

- [Указание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
