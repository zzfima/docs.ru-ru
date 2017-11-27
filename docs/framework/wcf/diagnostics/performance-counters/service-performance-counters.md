---
title: "Счетчики производительности службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: de51c6d0a3070f8bba8a2c77f9c028e7cfbc944d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="c00bf-102">Счетчики производительности службы</span><span class="sxs-lookup"><span data-stu-id="c00bf-102">Service Performance Counters</span></span>
<span data-ttu-id="c00bf-103">Счетчики производительности службы измеряют поведение службы в целом, их можно использовать для диагностики производительности всей службы.</span><span class="sxs-lookup"><span data-stu-id="c00bf-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="c00bf-104">При просмотре с помощью системного монитора (Perfmon.exe) счетчики находятся под объектом производительности `ServiceModelService 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="c00bf-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="c00bf-105">Экземпляры именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="c00bf-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="c00bf-106">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="c00bf-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="c00bf-107">Если длина имени экземпляра счетчика [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] превышает максимально допустимое значение, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.</span><span class="sxs-lookup"><span data-stu-id="c00bf-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00bf-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c00bf-108">See Also</span></span>  
 [<span data-ttu-id="c00bf-109">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="c00bf-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
