---
title: Метод ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 96ab77a36c0a0bddda0fca342433666dd19082d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426192"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="be0e7-102">Метод ICorProfilerCallback::JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="be0e7-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="be0e7-103">Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="be0e7-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be0e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be0e7-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be0e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be0e7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="be0e7-106">окне Идентификатор функции, для которой начинается компиляция.</span><span class="sxs-lookup"><span data-stu-id="be0e7-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="be0e7-107">окне Значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="be0e7-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="be0e7-108">Значение `true`, если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="be0e7-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="be0e7-109">Хотя значение `true` не будет нанести вред среде выполнения, оно может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="be0e7-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be0e7-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="be0e7-110">Remarks</span></span>  
 <span data-ttu-id="be0e7-111">Можно получить более одной пары `JITCompilationStarted` и [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов.</span><span class="sxs-lookup"><span data-stu-id="be0e7-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="be0e7-112">Например, среда выполнения начинает JIT-компилировать метод а, но необходимо запустить конструктор класса B.</span><span class="sxs-lookup"><span data-stu-id="be0e7-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="be0e7-113">Поэтому среда выполнения JIT компилирует конструктор для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="be0e7-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="be0e7-114">Пока конструктор выполняется, он вызывает метод а, что вызывает повторную JIT-компиляцию метода.</span><span class="sxs-lookup"><span data-stu-id="be0e7-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="be0e7-115">В этом сценарии первая JIT-компиляция метода A останавливается.</span><span class="sxs-lookup"><span data-stu-id="be0e7-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="be0e7-116">Однако обе попытки JIT-компиляции метода A сообщаются с событиями JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="be0e7-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="be0e7-117">Если профилировщик будет заменять код промежуточного языка MSIL для метода а путем вызова метода [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) , он должен сделать это для обоих событий `JITCompilationStarted`, но может использовать один и тот же блок MSIL для обоих.</span><span class="sxs-lookup"><span data-stu-id="be0e7-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="be0e7-118">Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, когда два потока одновременно осуществляют обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="be0e7-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="be0e7-119">Например, поток а вызывает `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="be0e7-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="be0e7-120">Однако до того, как поток A вызовет `JITCompilationFinished`, поток B вызывает [ICorProfilerCallback:: ексцептионсеарчфунктионентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `JITCompilationStarted` потока A.</span><span class="sxs-lookup"><span data-stu-id="be0e7-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="be0e7-121">Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов `JITCompilationFinished`.</span><span class="sxs-lookup"><span data-stu-id="be0e7-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="be0e7-122">Однако в таком случае идентификатор функции является допустимым.</span><span class="sxs-lookup"><span data-stu-id="be0e7-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be0e7-123">Требования</span><span class="sxs-lookup"><span data-stu-id="be0e7-123">Requirements</span></span>  
 <span data-ttu-id="be0e7-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be0e7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be0e7-125">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="be0e7-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="be0e7-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be0e7-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be0e7-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be0e7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0e7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="be0e7-128">See also</span></span>

- [<span data-ttu-id="be0e7-129">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="be0e7-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="be0e7-130">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="be0e7-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
