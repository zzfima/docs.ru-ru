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
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866238"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="30356-102">Метод ICorProfilerCallback::JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="30356-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="30356-103">Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.</span><span class="sxs-lookup"><span data-stu-id="30356-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30356-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30356-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30356-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30356-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="30356-106">окне Идентификатор функции, для которой начинается компиляция.</span><span class="sxs-lookup"><span data-stu-id="30356-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="30356-107">окне Значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="30356-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="30356-108">Значение `true`, если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="30356-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="30356-109">Хотя значение `true` не будет нанести вред среде выполнения, оно может исказить результаты профилирования.</span><span class="sxs-lookup"><span data-stu-id="30356-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30356-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="30356-110">Remarks</span></span>  
 <span data-ttu-id="30356-111">Можно получить более одной пары `JITCompilationStarted` и [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов.</span><span class="sxs-lookup"><span data-stu-id="30356-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="30356-112">Например, среда выполнения начинает JIT-компилировать метод а, но необходимо запустить конструктор класса B.</span><span class="sxs-lookup"><span data-stu-id="30356-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="30356-113">Поэтому среда выполнения JIT компилирует конструктор для класса B и запускает его.</span><span class="sxs-lookup"><span data-stu-id="30356-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="30356-114">Пока конструктор выполняется, он вызывает метод а, что вызывает повторную JIT-компиляцию метода.</span><span class="sxs-lookup"><span data-stu-id="30356-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="30356-115">В этом сценарии первая JIT-компиляция метода A останавливается.</span><span class="sxs-lookup"><span data-stu-id="30356-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="30356-116">Однако обе попытки JIT-компиляции метода A сообщаются с событиями JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="30356-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="30356-117">Если профилировщик будет заменять код промежуточного языка MSIL для метода а путем вызова метода [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) , он должен сделать это для обоих событий `JITCompilationStarted`, но может использовать один и тот же блок MSIL для обоих.</span><span class="sxs-lookup"><span data-stu-id="30356-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="30356-118">Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, когда два потока одновременно осуществляют обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="30356-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="30356-119">Например, поток а вызывает `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="30356-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="30356-120">Однако до того, как поток A вызовет `JITCompilationFinished`, поток B вызывает [ICorProfilerCallback:: ексцептионсеарчфунктионентер](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `JITCompilationStarted` потока A.</span><span class="sxs-lookup"><span data-stu-id="30356-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="30356-121">Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов `JITCompilationFinished`.</span><span class="sxs-lookup"><span data-stu-id="30356-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="30356-122">Однако в таком случае идентификатор функции является допустимым.</span><span class="sxs-lookup"><span data-stu-id="30356-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30356-123">Требования</span><span class="sxs-lookup"><span data-stu-id="30356-123">Requirements</span></span>  
 <span data-ttu-id="30356-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30356-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30356-125">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30356-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30356-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30356-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30356-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30356-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30356-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="30356-128">See also</span></span>

- [<span data-ttu-id="30356-129">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="30356-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="30356-130">Метод JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="30356-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
