---
title: Интерфейс ICorProfilerCallback4
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: a3394820f673e35777e1749229d4f8319841ca58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439393"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="def4e-102">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="def4e-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="def4e-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span><span class="sxs-lookup"><span data-stu-id="def4e-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="def4e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="def4e-104">Methods</span></span>  
  
|<span data-ttu-id="def4e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="def4e-105">Method</span></span>|<span data-ttu-id="def4e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="def4e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="def4e-107">Метод GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="def4e-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="def4e-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span><span class="sxs-lookup"><span data-stu-id="def4e-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="def4e-109">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="def4e-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="def4e-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span><span class="sxs-lookup"><span data-stu-id="def4e-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="def4e-111">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="def4e-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="def4e-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span><span class="sxs-lookup"><span data-stu-id="def4e-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="def4e-113">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="def4e-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="def4e-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span><span class="sxs-lookup"><span data-stu-id="def4e-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="def4e-115">Метод ReJITError</span><span class="sxs-lookup"><span data-stu-id="def4e-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="def4e-116">Reports an error encountered while processing a recompile request.</span><span class="sxs-lookup"><span data-stu-id="def4e-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="def4e-117">Метод SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="def4e-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="def4e-118">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="def4e-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="def4e-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="def4e-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="def4e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="def4e-120">Requirements</span></span>  
 <span data-ttu-id="def4e-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="def4e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def4e-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="def4e-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="def4e-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def4e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="def4e-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def4e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def4e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="def4e-125">See also</span></span>

- [<span data-ttu-id="def4e-126">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="def4e-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="def4e-127">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="def4e-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="def4e-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="def4e-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
