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
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077242"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="6221e-102">Интерфейс ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="6221e-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="6221e-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="6221e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6221e-104">Подкласс [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) , предоставляет метод обратного вызова, который среда CLR использует для уведомления профилировщика, загрузке сборки.</span><span class="sxs-lookup"><span data-stu-id="6221e-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6221e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6221e-105">Methods</span></span>  
  
|<span data-ttu-id="6221e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6221e-106">Method</span></span>|<span data-ttu-id="6221e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6221e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6221e-108">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="6221e-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="6221e-109">Уведомляет профилировщика о том, что сборка находится на очень ранней стадии загрузки, когда среда CLR выполняет обход замыкания ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="6221e-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6221e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6221e-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6221e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6221e-111">Requirements</span></span>  
 <span data-ttu-id="6221e-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6221e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6221e-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6221e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="6221e-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6221e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6221e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6221e-115">See also</span></span>

- [<span data-ttu-id="6221e-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="6221e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
