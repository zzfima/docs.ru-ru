---
title: "Счетчики производительности конечных точек"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 157f0cc5d860841940b0850ca3895f82a12d47ce
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-performance-counters"></a>Счетчики производительности конечных точек
Счетчики производительности конечных точек собирают данные о том, как именно конечные точки принимают сообщения. Их можно просмотреть с помощью системного монитора, выбрав объект производительности `ServiceModelEndpoint 4.0.0.0`. Экземплярам присваиваются имена согласно следующему шаблону:  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 Данные аналогичны собираемым для отдельных операций, но агрегируются только на конечной точке.  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена. Если длина имени экземпляра счетчика [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] превышает максимально допустимое значение, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.  
  
## <a name="see-also"></a>См. также  
 [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
