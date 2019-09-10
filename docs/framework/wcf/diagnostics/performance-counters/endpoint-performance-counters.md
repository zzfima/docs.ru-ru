---
title: Счетчики производительности конечных точек
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 72512a15d5b378b1ccb65995441f8f67e251febb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856095"
---
# <a name="endpoint-performance-counters"></a>Счетчики производительности конечных точек
Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения. Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`. Экземплярам присваиваются имена согласно следующему шаблону:  
  
`(ServiceName).(ContractName)@(endpoint listener address)`  
  
 Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.  
  
> [!CAUTION]
> Длина имени экземпляра счетчика производительности ограничена. Если имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра на хэш-значение.  
  
## <a name="see-also"></a>См. также

- [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
