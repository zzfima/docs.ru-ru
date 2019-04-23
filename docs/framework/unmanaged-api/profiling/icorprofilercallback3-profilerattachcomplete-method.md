---
title: Метод ICorProfilerCallback3::ProfilerAttachComplete
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6bd3326aa5807bd7f2dd882991d211cbbf873067
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150414"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="3f18f-102">Метод ICorProfilerCallback3::ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="3f18f-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="3f18f-103">Вызывается общеязыковой среды выполнения (CLR), чтобы указать, что теперь профилировщик может вызвать [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) и [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) дополнительные методы.</span><span class="sxs-lookup"><span data-stu-id="3f18f-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f18f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f18f-104">Syntax</span></span>  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3f18f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f18f-105">Remarks</span></span>  
 <span data-ttu-id="3f18f-106">`ProfilerAttachComplete` Обратного вызова выдается после [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="3f18f-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="3f18f-107">Он указывает следующее.</span><span class="sxs-lookup"><span data-stu-id="3f18f-107">It indicates the following:</span></span>  
  
-   <span data-ttu-id="3f18f-108">Обратные вызовы, которые были запрошены профилировщиком в `InitializeForAttach`, были активированы.</span><span class="sxs-lookup"><span data-stu-id="3f18f-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
-   <span data-ttu-id="3f18f-109">Профилировщик теперь может выполнять захват в связанных идентификаторах, не заботясь об отсутствующих уведомлениях.</span><span class="sxs-lookup"><span data-stu-id="3f18f-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="3f18f-110">Среда CLR игнорирует возвращаемое значение из этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3f18f-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f18f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3f18f-111">Requirements</span></span>  
 <span data-ttu-id="3f18f-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f18f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f18f-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f18f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3f18f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f18f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f18f-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f18f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f18f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3f18f-116">See also</span></span>

- [<span data-ttu-id="3f18f-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="3f18f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3f18f-118">Интерфейс ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="3f18f-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="3f18f-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="3f18f-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="3f18f-120">Профилирование</span><span class="sxs-lookup"><span data-stu-id="3f18f-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
