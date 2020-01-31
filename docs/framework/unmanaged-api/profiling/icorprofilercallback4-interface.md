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
ms.openlocfilehash: 1b85c48859ac29738347d112dd0466a76bfdfd2c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865341"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="dadbc-102">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="dadbc-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="dadbc-103">Предоставляет методы обратного вызова, используемые средой CLR для передачи информации в профилировщик.</span><span class="sxs-lookup"><span data-stu-id="dadbc-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dadbc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dadbc-104">Methods</span></span>  
  
|<span data-ttu-id="dadbc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dadbc-105">Method</span></span>|<span data-ttu-id="dadbc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dadbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dadbc-107">Метод GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="dadbc-107">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="dadbc-108">Позволяет профилировщику кода устанавливать альтернативные флаги создания кода для нового текста перекомпилированного метода.</span><span class="sxs-lookup"><span data-stu-id="dadbc-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="dadbc-109">Метод MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="dadbc-109">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="dadbc-110">Сообщает о новом макете объектов в куче в результате сборки мусора для сжатия.</span><span class="sxs-lookup"><span data-stu-id="dadbc-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="dadbc-111">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="dadbc-111">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="dadbc-112">Уведомляет профилировщик о том, что JIT-компилятор завершил повторную компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="dadbc-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="dadbc-113">Метод ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="dadbc-113">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="dadbc-114">Уведомляет профилировщик о том, что JIT-компилятор начал перекомпилировать функцию.</span><span class="sxs-lookup"><span data-stu-id="dadbc-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="dadbc-115">Метод ReJITError</span><span class="sxs-lookup"><span data-stu-id="dadbc-115">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="dadbc-116">Сообщает об ошибке, возникшей при обработке запроса на перекомпиляцию.</span><span class="sxs-lookup"><span data-stu-id="dadbc-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="dadbc-117">Метод SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="dadbc-117">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="dadbc-118">Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия.</span><span class="sxs-lookup"><span data-stu-id="dadbc-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dadbc-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="dadbc-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dadbc-120">Требования</span><span class="sxs-lookup"><span data-stu-id="dadbc-120">Requirements</span></span>  
 <span data-ttu-id="dadbc-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dadbc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dadbc-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dadbc-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dadbc-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dadbc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dadbc-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dadbc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dadbc-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="dadbc-125">See also</span></span>

- [<span data-ttu-id="dadbc-126">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="dadbc-126">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="dadbc-127">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="dadbc-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="dadbc-128">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="dadbc-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
