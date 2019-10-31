---
title: Интерфейс ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: f8c2fb544cf9fd6642bd0581211e0e4e49633221
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139769"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="67bfe-102">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="67bfe-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="67bfe-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="67bfe-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="67bfe-104">Подкласс [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="67bfe-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67bfe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="67bfe-105">Methods</span></span>  
  
|<span data-ttu-id="67bfe-106">Метод</span><span class="sxs-lookup"><span data-stu-id="67bfe-106">Method</span></span>|<span data-ttu-id="67bfe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="67bfe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67bfe-108">Метод ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="67bfe-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="67bfe-109">Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="67bfe-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67bfe-110">Требования</span><span class="sxs-lookup"><span data-stu-id="67bfe-110">Requirements</span></span>  
 <span data-ttu-id="67bfe-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67bfe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67bfe-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67bfe-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67bfe-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67bfe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67bfe-114">См. также</span><span class="sxs-lookup"><span data-stu-id="67bfe-114">See also</span></span>

- [<span data-ttu-id="67bfe-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="67bfe-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
