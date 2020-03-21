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
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177083"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="41bc5-102">Метод ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="41bc5-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="41bc5-103">Уведомляет профайлера о том, что компилятор JIT(IIT) начал перекомпилировать функцию.</span><span class="sxs-lookup"><span data-stu-id="41bc5-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41bc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41bc5-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41bc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41bc5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="41bc5-106">(в) Идентификатор функции, которую начал пересоставлять компилятор JIT.</span><span class="sxs-lookup"><span data-stu-id="41bc5-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="41bc5-107">(в) Идентификатор перекомпиляции новой версии функции.</span><span class="sxs-lookup"><span data-stu-id="41bc5-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="41bc5-108">(в) `true` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного вызова; `false` указать, что блокировка не повлияет на работу времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="41bc5-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="41bc5-109">Значение `true` не наносит ущерба времени выполнения, но может повлиять на результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="41bc5-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41bc5-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="41bc5-110">Remarks</span></span>  
 <span data-ttu-id="41bc5-111">Можно получить более одной пары `ReJITCompilationStarted` и [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) метод требует для каждой функции из-за того, как время выполнения обрабатывает конструкторов класса.</span><span class="sxs-lookup"><span data-stu-id="41bc5-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="41bc5-112">Например, время выполнения начинает перекомпилировать метод A, но необходимо запустить конструктор класса для класса B.</span><span class="sxs-lookup"><span data-stu-id="41bc5-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="41bc5-113">Таким образом, время выполнения перекомпилирует конструктор для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="41bc5-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="41bc5-114">Во время работы конструктора он вызывает метод А, который приводит к повторному компилированию метода А.</span><span class="sxs-lookup"><span data-stu-id="41bc5-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="41bc5-115">В этом сценарии первая перекомпиляция метода А останавливается.</span><span class="sxs-lookup"><span data-stu-id="41bc5-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="41bc5-116">Однако обе попытки перекомпилировать метод А сообщаются с событиями перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="41bc5-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="41bc5-117">Профилеры должны поддерживать последовательность обратных вызовов перекомпийки JIT в тех случаях, когда два потока одновременно делают обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="41bc5-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="41bc5-118">Например, вызовы `ReJITCompilationStarted`потока А; однако, прежде чем поток A вызывает [ReJITCompilationFinished,](icorprofilercallback4-rejitcompilationfinished-method.md)поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции от `ReJITCompilationStarted` обратного вызова для потока A. Может показаться, что идентификатор функции еще не должен быть действительным, поскольку вызов [в ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) еще не был получен профайлером.</span><span class="sxs-lookup"><span data-stu-id="41bc5-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="41bc5-119">Однако в этом случае идентификатор функции действителен.</span><span class="sxs-lookup"><span data-stu-id="41bc5-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41bc5-120">Требования</span><span class="sxs-lookup"><span data-stu-id="41bc5-120">Requirements</span></span>  
 <span data-ttu-id="41bc5-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41bc5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41bc5-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41bc5-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41bc5-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41bc5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41bc5-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41bc5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41bc5-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="41bc5-125">See also</span></span>

- [<span data-ttu-id="41bc5-126">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="41bc5-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="41bc5-127">Интерфейс ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="41bc5-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="41bc5-128">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="41bc5-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="41bc5-129">Метод ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="41bc5-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
