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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205138"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="7774a-102">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="7774a-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="7774a-103">Предоставляет методы обратного вызова, среда CLR (CLR) использует для передачи сведений профилировщику.</span><span class="sxs-lookup"><span data-stu-id="7774a-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7774a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7774a-104">Methods</span></span>  
  
|<span data-ttu-id="7774a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7774a-105">Method</span></span>|<span data-ttu-id="7774a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7774a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7774a-107">Метод GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="7774a-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="7774a-108">Позволяет задать флаги создания альтернативного кода для нового тела метода перекомпилированной профилировщику кода.</span><span class="sxs-lookup"><span data-stu-id="7774a-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="7774a-109">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="7774a-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="7774a-110">Сообщает о структуре объектов в куче в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7774a-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="7774a-111">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7774a-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="7774a-112">Уведомляет профилировщик об окончании повторной компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="7774a-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="7774a-113">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="7774a-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="7774a-114">Уведомляет профилировщик о начале повторной компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="7774a-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="7774a-115">Метод ReJITError</span><span class="sxs-lookup"><span data-stu-id="7774a-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="7774a-116">Сообщает об ошибке при обработке запроса recompile.</span><span class="sxs-lookup"><span data-stu-id="7774a-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="7774a-117">Метод SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="7774a-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="7774a-118">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="7774a-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7774a-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="7774a-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7774a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="7774a-120">Requirements</span></span>  
 <span data-ttu-id="7774a-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7774a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7774a-122">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7774a-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7774a-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7774a-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7774a-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7774a-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7774a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7774a-125">See also</span></span>

- [<span data-ttu-id="7774a-126">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7774a-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="7774a-127">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7774a-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="7774a-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="7774a-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
