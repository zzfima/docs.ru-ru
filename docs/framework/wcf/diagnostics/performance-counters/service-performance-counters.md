---
title: Счетчики производительности службы
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: 929ddcb2f271b7488270ea39e7a3a0037158c855
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320026"
---
# <a name="service-performance-counters"></a>Счетчики производительности службы
Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы. При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`. Экземпляры именуются по следующей схеме:  
  
`ServiceName@ServiceBaseAddress`
  
> [!CAUTION]
> Длина имени экземпляра счетчика производительности ограничена. Если имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра на хэш-значение.  
  
## <a name="see-also"></a>См. также

- [Счетчики производительности](index.md)
