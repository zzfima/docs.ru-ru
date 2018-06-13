---
title: Счетчики производительности службы
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bdc68fd2b629c538c097dab4e1cf3f89b7f3a091
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810191"
---
# <a name="service-performance-counters"></a><span data-ttu-id="9b695-102">Счетчики производительности службы</span><span class="sxs-lookup"><span data-stu-id="9b695-102">Service Performance Counters</span></span>
<span data-ttu-id="9b695-103">Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы.</span><span class="sxs-lookup"><span data-stu-id="9b695-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="9b695-104">При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="9b695-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="9b695-105">Экземпляры именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="9b695-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="9b695-106">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="9b695-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="9b695-107">Имя экземпляра счетчика Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значением хэша.</span><span class="sxs-lookup"><span data-stu-id="9b695-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b695-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9b695-108">See Also</span></span>  
 [<span data-ttu-id="9b695-109">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="9b695-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
