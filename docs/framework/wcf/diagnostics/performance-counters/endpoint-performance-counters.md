---
title: Счетчики производительности конечных точек
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803141"
---
# <a name="endpoint-performance-counters"></a>Счетчики производительности конечных точек
Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения. Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`. Экземплярам присваиваются имена согласно следующему шаблону:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена. Имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значением хэша.  
  
## <a name="see-also"></a>См. также  
 [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
