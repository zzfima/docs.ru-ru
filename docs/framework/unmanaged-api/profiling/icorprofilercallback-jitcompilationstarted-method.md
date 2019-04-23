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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075325"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="8a375-102">Метод ICorProfilerCallback::JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="8a375-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="8a375-103">Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="8a375-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a375-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a375-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a375-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a375-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8a375-106">[in] Идентификатор функции, для которого выполняется запуск компиляции.</span><span class="sxs-lookup"><span data-stu-id="8a375-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="8a375-107">[in] Значение, указывающее профилировщику ли блокировка повлияет на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8a375-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="8a375-108">Значение равно `true` Если блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="8a375-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="8a375-109">Несмотря на то что значение `true` не представляет угрозы для среды выполнения, он может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="8a375-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a375-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a375-110">Remarks</span></span>  
 <span data-ttu-id="8a375-111">Возможно, для получения более чем одну пару `JITCompilationStarted` и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="8a375-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="8a375-112">Например среда выполнения начинает JIT-компиляцию метода, но конструктор класса для класса B нужно выполнить.</span><span class="sxs-lookup"><span data-stu-id="8a375-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="8a375-113">Таким образом, среда выполнения JIT-компиляцию конструктора для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="8a375-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="8a375-114">Во время работы конструктора, он делает вызов метода А, который вызывает метод A, который нужно JIT-компиляции, чтобы снова.</span><span class="sxs-lookup"><span data-stu-id="8a375-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="8a375-115">В этом случае первый JIT-компиляцию метода A прерывается.</span><span class="sxs-lookup"><span data-stu-id="8a375-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="8a375-116">Тем не менее обе попытки JIT-компиляцию метода A выводятся с событиями JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="8a375-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="8a375-117">Если профилировщик будет заменить код на промежуточном языке (MSIL) для метода типа путем вызова [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метод, она должна будет работать для обоих `JITCompilationStarted` события, но он может использовать того же блока MSIL для обоих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="8a375-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="8a375-118">Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, где два потока одновременно осуществляют обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="8a375-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="8a375-119">Например, поток A вызывает `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="8a375-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="8a375-120">Тем не менее, прежде чем поток A вызывает `JITCompilationFinished`, поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с Идентификатором потока A, который функция `JITCompilationStarted` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="8a375-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="8a375-121">Может показаться, что идентификатор функции должно находиться допустимым так как вызов `JITCompilationFinished` еще не получил профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="8a375-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="8a375-122">Тем не менее в случае такого рода, идентификатор функции является допустимым.</span><span class="sxs-lookup"><span data-stu-id="8a375-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a375-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8a375-123">Requirements</span></span>  
 <span data-ttu-id="8a375-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a375-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a375-125">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a375-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a375-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a375-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a375-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a375-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a375-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8a375-128">See also</span></span>

- [<span data-ttu-id="8a375-129">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8a375-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8a375-130">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="8a375-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
