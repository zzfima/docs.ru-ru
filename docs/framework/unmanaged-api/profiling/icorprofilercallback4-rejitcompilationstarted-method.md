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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865198"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="7dfdb-102">Метод ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="7dfdb-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="7dfdb-103">Уведомляет профилировщик о том, что JIT-компилятор начал перекомпилировать функцию.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfdb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7dfdb-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dfdb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7dfdb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7dfdb-106">окне Идентификатор функции, которая была запущена JIT-компилятором для перекомпиляции.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="7dfdb-107">окне Идентификатор повторной компиляции новой версии функции.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="7dfdb-108">[in] `true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="7dfdb-109">Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfdb-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="7dfdb-110">Remarks</span></span>  
 <span data-ttu-id="7dfdb-111">Можно получить более одной пары вызовов методов `ReJITCompilationStarted` и [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="7dfdb-112">Например, среда выполнения начинает перекомпилировать метод а, но необходимо запустить конструктор класса для класса B.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="7dfdb-113">Таким образом, среда выполнения перекомпилирует конструктор для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="7dfdb-114">Пока конструктор выполняется, он вызывает метод а, что вызывает повторную компиляцию метода а.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="7dfdb-115">В этом сценарии первая перекомпиляция метода A останавливается.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="7dfdb-116">Однако обе попытки перекомпилировать метод а сообщают о событиях JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="7dfdb-117">Профилировщики должны поддерживать последовательность обратных вызовов JIT-компиляции в случаях, когда два потока одновременно осуществляют обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="7dfdb-118">Например, поток A вызывает `ReJITCompilationStarted`; Однако прежде чем поток A вызовет [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback:: ексцептионсеарчфунктионентер](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `ReJITCompilationStarted` для потока а. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7dfdb-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="7dfdb-119">Однако в этом случае идентификатор функции является допустимым.</span><span class="sxs-lookup"><span data-stu-id="7dfdb-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dfdb-120">Требования</span><span class="sxs-lookup"><span data-stu-id="7dfdb-120">Requirements</span></span>  
 <span data-ttu-id="7dfdb-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dfdb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dfdb-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7dfdb-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7dfdb-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dfdb-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dfdb-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dfdb-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfdb-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="7dfdb-125">See also</span></span>

- [<span data-ttu-id="7dfdb-126">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7dfdb-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7dfdb-127">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="7dfdb-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="7dfdb-128">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7dfdb-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="7dfdb-129">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7dfdb-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
