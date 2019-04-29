---
title: Счетчики производительности конечных точек
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: f07e318e39a68e689ec484b09fa743623cfb51d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797232"
---
# <a name="endpoint-performance-counters"></a>Счетчики производительности конечных точек
Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения. Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`. Экземплярам присваиваются имена согласно следующему шаблону:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена. Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.  
  
## <a name="see-also"></a>См. также

- [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
