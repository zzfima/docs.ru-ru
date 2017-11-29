---
title: "Интерфейс ICorProfilerCallback4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4
helpviewer_keywords: ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64a26f5dfb0ad9f06bb1b9eb31dcae36f4623c4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="f132d-102">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="f132d-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="f132d-103">Предоставляет методы обратного вызова, используемые для передачи сведений профилировщику общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="f132d-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f132d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f132d-104">Methods</span></span>  
  
|<span data-ttu-id="f132d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f132d-105">Method</span></span>|<span data-ttu-id="f132d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f132d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f132d-107">Метод GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="f132d-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="f132d-108">Позволяет задать флаги создания дополнительного кода для нового тела метода перекомпилированной профилировщику кода.</span><span class="sxs-lookup"><span data-stu-id="f132d-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="f132d-109">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="f132d-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="f132d-110">Сообщает о новой структуре объектов в куче в результате сжатия сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="f132d-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="f132d-111">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="f132d-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="f132d-112">Уведомляет профилировщик об окончании повторная компиляция функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="f132d-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="f132d-113">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f132d-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="f132d-114">Уведомляет профилировщик, что компилятор just-in-time (JIT) запущена в повторной компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="f132d-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="f132d-115">Метод ReJITError</span><span class="sxs-lookup"><span data-stu-id="f132d-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="f132d-116">Сообщает об ошибке при обработке запроса recompile.</span><span class="sxs-lookup"><span data-stu-id="f132d-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="f132d-117">Метод SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="f132d-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="f132d-118">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="f132d-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f132d-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="f132d-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f132d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="f132d-120">Requirements</span></span>  
 <span data-ttu-id="f132d-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f132d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f132d-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f132d-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f132d-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f132d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f132d-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f132d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f132d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f132d-125">See Also</span></span>  
 [<span data-ttu-id="f132d-126">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="f132d-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="f132d-127">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="f132d-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f132d-128">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f132d-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
