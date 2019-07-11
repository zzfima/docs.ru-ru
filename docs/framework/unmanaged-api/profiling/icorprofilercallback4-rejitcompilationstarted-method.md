---
title: Метод ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 58293929b576493d3751f9ce30ba00cec92e180c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758162"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="2022b-102">Метод ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="2022b-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="2022b-103">Уведомляет профилировщик о начале повторной компиляции функции компилятор just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="2022b-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2022b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2022b-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2022b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2022b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2022b-106">[in] Идентификатор функции, JIT-компилятор начал перекомпилировать.</span><span class="sxs-lookup"><span data-stu-id="2022b-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="2022b-107">[in] Повторная компиляция идентификатор новой версии функции.</span><span class="sxs-lookup"><span data-stu-id="2022b-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="2022b-108">[in] `true` для указания, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="2022b-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="2022b-109">Значение `true` не повреждает среды выполнения, но могут повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="2022b-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2022b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2022b-110">Remarks</span></span>  
 <span data-ttu-id="2022b-111">Возможно, для получения более чем одну пару `ReJITCompilationStarted` и [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) метод вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="2022b-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="2022b-112">Например среда выполнения начинает перекомпилировать метод A, но конструктор класса для класса B нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="2022b-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="2022b-113">Таким образом среда выполнения повторных компиляций конструктор для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="2022b-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="2022b-114">Во время работы конструктора, он делает вызов метода А, который вызывает метод A попытку повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="2022b-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="2022b-115">В этом случае первый перекомпиляция метод A будет прерван.</span><span class="sxs-lookup"><span data-stu-id="2022b-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="2022b-116">Тем не менее оба пытается перекомпилировать метод являются сообщил с события перекомпиляции JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="2022b-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="2022b-117">Профилировщики должны поддерживать последовательность обратных вызовов для перекомпиляции JIT в случаях, где два потока одновременно осуществляют обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="2022b-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="2022b-118">Например, поток A вызывает `ReJITCompilationStarted`; тем не менее, прежде чем поток A вызывает [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с ИД функции из `ReJITCompilationStarted` обратного вызова для потока A. Может показаться, что идентификатор функции должно находиться допустимым так как вызов [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) еще не получил профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="2022b-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="2022b-119">Однако в этом случае идентификатор функции недопустим.</span><span class="sxs-lookup"><span data-stu-id="2022b-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2022b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2022b-120">Requirements</span></span>  
 <span data-ttu-id="2022b-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2022b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2022b-122">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2022b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2022b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2022b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2022b-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2022b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2022b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2022b-125">See also</span></span>

- [<span data-ttu-id="2022b-126">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2022b-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2022b-127">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="2022b-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="2022b-128">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="2022b-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="2022b-129">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="2022b-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
