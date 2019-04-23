---
title: Счетчики производительности операций
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: d4f5755129fecb62e6a4da98a2bf642c5e20f9c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077112"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="98d19-102">Счетчики производительности операций</span><span class="sxs-lookup"><span data-stu-id="98d19-102">Operation Performance Counters</span></span>
<span data-ttu-id="98d19-103">При просмотре с помощью системного монитора (Perfmon.exe) счетчики производительности операций находятся под объектом производительности `ServiceModelOperation 4.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="98d19-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="98d19-104">Каждая операция содержит отдельный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="98d19-104">Each operation has an individual instance.</span></span> <span data-ttu-id="98d19-105">Следовательно, если указанный контракт имеет 10 операций, 10 экземпляров счетчика операций связаны с этим контрактом.</span><span class="sxs-lookup"><span data-stu-id="98d19-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="98d19-106">Экземпляры объекта именуются по следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="98d19-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="98d19-107">Этот счетчик позволяет измерить, как используется вызов и насколько успешно выполняется операция.</span><span class="sxs-lookup"><span data-stu-id="98d19-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="98d19-108">Длина имени экземпляра счетчика производительности ограничена.</span><span class="sxs-lookup"><span data-stu-id="98d19-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="98d19-109">Имя экземпляра счетчика службы Windows Communication Foundation (WCF) превышает максимальную длину, WCF заменяет часть имени экземпляра значение хэша.</span><span class="sxs-lookup"><span data-stu-id="98d19-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d19-110">См. также</span><span class="sxs-lookup"><span data-stu-id="98d19-110">See also</span></span>

- [<span data-ttu-id="98d19-111">Счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="98d19-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
