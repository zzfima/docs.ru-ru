---
title: "Интерфейс ICorProfilerCallback7"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8eb370e4f16212c536c252661163b7eca6f74d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="7c143-102">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="7c143-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="7c143-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="7c143-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="7c143-104">Подкласс [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="7c143-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c143-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7c143-105">Methods</span></span>  
  
|<span data-ttu-id="7c143-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7c143-106">Method</span></span>|<span data-ttu-id="7c143-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7c143-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c143-108">Метод ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="7c143-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="7c143-109">Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="7c143-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c143-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7c143-110">Requirements</span></span>  
 <span data-ttu-id="7c143-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c143-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c143-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c143-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c143-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c143-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c143-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7c143-114">See Also</span></span>  
 [<span data-ttu-id="7c143-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="7c143-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
