---
title: Счетчики производительности службы
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: dc31e05f82f232095f6560c8fdd9bf75c040e2ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210416"
---
# <a name="service-performance-counters"></a>Счетчики производительности службы
Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы. При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`. Экземпляры именуются по следующей схеме:  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  Длина имени экземпляра счетчика производительности ограничена. Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.  
  
## <a name="see-also"></a>См. также

- [Счетчики производительности](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
