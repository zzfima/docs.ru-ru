---
title: "Метод ICorProfilerCallback4::ReJITCompilationStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c484e-102">Метод ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c484e-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c484e-103">Уведомляет профилировщик, что компилятор just-in-time (JIT) запущена в повторной компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="c484e-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c484e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c484e-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c484e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c484e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c484e-106">[in] Идентификатор функции, начатое JIT-компилятором для перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="c484e-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c484e-107">[in] Повторная компиляция идентификатор новой версии функции.</span><span class="sxs-lookup"><span data-stu-id="c484e-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c484e-108">[in] `true` для указания, что блокировка может послужить причиной среды выполнения для ожидания вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c484e-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c484e-109">Значение `true` не представляет угрозы для среды выполнения, но может повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="c484e-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c484e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c484e-110">Remarks</span></span>  
 <span data-ttu-id="c484e-111">Можно получить более чем одну пару `ReJITCompilationStarted` и [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) метод вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="c484e-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c484e-112">Например среда выполнения начинает перекомпилировать метод A, но конструктор класса для класса B должна быть запущена.</span><span class="sxs-lookup"><span data-stu-id="c484e-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c484e-113">Таким образом среда выполнения повторных компиляций конструктора для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="c484e-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c484e-114">Пока конструктор работает, он вызывает метод A, вызывая метод A попытку повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="c484e-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c484e-115">В этом случае перекомпиляция первый метод A прерывается.</span><span class="sxs-lookup"><span data-stu-id="c484e-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c484e-116">Тем не менее оба предпринимается попытка повторной компиляции метода являются этот отчет события перекомпиляции JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="c484e-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c484e-117">Профилировщики должны поддерживать последовательность обратных вызовов для перекомпиляции JIT в случаях, где два потока одновременно осуществляют обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="c484e-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c484e-118">Например, поток A вызывает `ReJITCompilationStarted`; тем не менее, прежде чем поток A вызывает метод [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатор функции из `ReJITCompilationStarted` обратного вызова для потока, а. Кажется, что идентификатор функции должно находиться допустимым из-за вызова [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) еще не получил профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="c484e-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c484e-119">Однако в этом случае идентификатор функции является допустимым.</span><span class="sxs-lookup"><span data-stu-id="c484e-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c484e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c484e-120">Requirements</span></span>  
 <span data-ttu-id="c484e-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c484e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c484e-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c484e-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c484e-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c484e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c484e-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c484e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c484e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c484e-125">See Also</span></span>  
 [<span data-ttu-id="c484e-126">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c484e-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c484e-127">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="c484e-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="c484e-128">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c484e-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="c484e-129">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c484e-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
