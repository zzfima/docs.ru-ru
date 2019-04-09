---
title: Счетчики производительности операций
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: d4f5755129fecb62e6a4da98a2bf642c5e20f9c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077112"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="ec8e4-102">Счетчики производительности операций</span><span class="sxs-lookup"><span data-stu-id="ec8e4-102">Operation Performance Counters</span></span>
<span data-ttu-id="ec8e4-103">При просмотре с помощью системного монитора (Perfmon.exe) счетчики производительности операций находятся под объектом производительности `ServiceModelOperation 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="ec8e4-104">Каждая операция содержит отдельный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-104">Each operation has an individual instance.</span></span> <span data-ttu-id="ec8e4-105">Следовательно, если указанный контракт имеет 10 операций, 10 экземпляров счетчика операций связаны с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="ec8e4-106">Экземпляры объекта именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="ec8e4-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="ec8e4-107">Этот счетчик позволяет измерить, как используется вызов и насколько успешно выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ec8e4-108">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="ec8e4-109">Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.</span><span class="sxs-lookup"><span data-stu-id="ec8e4-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8e4-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ec8e4-110">See also</span></span>

- [<span data-ttu-id="ec8e4-111">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="ec8e4-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
