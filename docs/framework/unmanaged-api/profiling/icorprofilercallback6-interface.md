---
title: Интерфейс ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5025f4bb6433d193ecf7dec1d8375104147e9e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562574"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="6d5bb-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="6d5bb-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="6d5bb-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="6d5bb-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6d5bb-104">Подкласс [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , предоставляет метод обратного вызова, который среда CLR использует для уведомления профилировщика, загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d5bb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6d5bb-105">Methods</span></span>  
  
|<span data-ttu-id="6d5bb-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6d5bb-106">Method</span></span>|<span data-ttu-id="6d5bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6d5bb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d5bb-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="6d5bb-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="6d5bb-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="6d5bb-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d5bb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d5bb-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d5bb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6d5bb-111">Requirements</span></span>  
 <span data-ttu-id="6d5bb-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d5bb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d5bb-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d5bb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d5bb-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d5bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5bb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6d5bb-115">See also</span></span>
- [<span data-ttu-id="6d5bb-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="6d5bb-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
