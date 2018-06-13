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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f681001b610f42fef28181ffe3b47d702aabdf6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452697"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="dfda2-102">Интерфейс ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="dfda2-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="dfda2-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="dfda2-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="dfda2-104">Подкласс [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) , который предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика, что обновляется поток символов, связанный с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="dfda2-104">A subclass of [ICorProfilerCallback6](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dfda2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dfda2-105">Methods</span></span>  
  
|<span data-ttu-id="dfda2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="dfda2-106">Method</span></span>|<span data-ttu-id="dfda2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dfda2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dfda2-108">Метод ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="dfda2-108">ModuleInMemorySymbolsUpdated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="dfda2-109">Уведомляет профилировщик об обновлении потока символов, связанного с модулем в памяти.</span><span class="sxs-lookup"><span data-stu-id="dfda2-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfda2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="dfda2-110">Requirements</span></span>  
 <span data-ttu-id="dfda2-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfda2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfda2-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dfda2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dfda2-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfda2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfda2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dfda2-114">See Also</span></span>  
 [<span data-ttu-id="dfda2-115">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="dfda2-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
