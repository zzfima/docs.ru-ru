---
title: "Счетчики производительности операций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 83460e1c4db17938466051269dbeba3f19e0b40a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="operation-performance-counters"></a><span data-ttu-id="0fc5a-102">Счетчики производительности операций</span><span class="sxs-lookup"><span data-stu-id="0fc5a-102">Operation Performance Counters</span></span>
<span data-ttu-id="0fc5a-103">При просмотре с помощью системного монитора (Perfmon.exe) счетчики производительности операций находятся под объектом производительности `ServiceModelOperation 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="0fc5a-104">Каждая операция содержит отдельный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-104">Each operation has an individual instance.</span></span> <span data-ttu-id="0fc5a-105">Следовательно, если указанный контракт имеет 10 операций, 10 экземпляров счетчика операций связаны с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="0fc5a-106">Экземпляры объекта именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="0fc5a-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="0fc5a-107">Этот счетчик позволяет измерить, как используется вызов и насколько успешно выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0fc5a-108">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="0fc5a-109">Если длина имени экземпляра счетчика [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] превышает максимально допустимое значение, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] заменяет часть имени экземпляра значением хэша.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-109">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc5a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0fc5a-110">See Also</span></span>  
 [<span data-ttu-id="0fc5a-111">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="0fc5a-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
