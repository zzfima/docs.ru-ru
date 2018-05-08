---
title: Счетчики производительности службы
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 71eff5c656a4782056ac518f105f73bc549da336
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="service-performance-counters"></a>Счетчики производительности службы
Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы. При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`. Экземпляры именуются по следующей схеме:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена. Если имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.  
  
## <a name="see-also"></a>См. также  
 [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
