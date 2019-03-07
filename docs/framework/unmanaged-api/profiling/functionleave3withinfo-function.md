---
title: Функция FunctionLeave3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 714514d5b6a36d028da442bcc05accc0686417cf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500620"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="c7906-102">Функция FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c7906-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="c7906-103">Уведомляет профилировщик, что элемент управления возвращается из функции и предоставляет маркер, который может быть передан [метод ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для извлечения кадра стека и возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="c7906-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7906-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7906-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7906-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7906-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="c7906-106">[in] Идентификатор функции, из которого возвращается.</span><span class="sxs-lookup"><span data-stu-id="c7906-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="c7906-107">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="c7906-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="c7906-108">Этот дескриптор допустим только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="c7906-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7906-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7906-109">Remarks</span></span>  
 <span data-ttu-id="c7906-110">`FunctionLeave3WithInfo` Метод обратного вызова Уведомляет профилировщик, как функции, называются, а также позволяет профилировщику использовать [метод ICorProfilerInfo3::GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) проверять возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="c7906-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="c7906-111">Для доступа к информации возвращаемое значение `COR_PRF_ENABLE_FUNCTION_RETVAL` флаг должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="c7906-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="c7906-112">Можно использовать профилировщик [метод ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) установить флаги событий, а затем использовать [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации вашей Реализация этой функции.</span><span class="sxs-lookup"><span data-stu-id="c7906-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="c7906-113">`FunctionLeave3WithInfo` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="c7906-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="c7906-114">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="c7906-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="c7906-115">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="c7906-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="c7906-116">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="c7906-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="c7906-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="c7906-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c7906-118">Реализация `FunctionLeave3WithInfo` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c7906-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="c7906-119">Реализация не должны в сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c7906-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c7906-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave3WithInfo` возвращает.</span><span class="sxs-lookup"><span data-stu-id="c7906-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="c7906-121">`FunctionLeave3WithInfo` Функция не должна вызов управляемого кода или инициировать распределение управляемой памяти любым способом.</span><span class="sxs-lookup"><span data-stu-id="c7906-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7906-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c7906-122">Requirements</span></span>  
 <span data-ttu-id="c7906-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7906-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7906-124">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c7906-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c7906-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7906-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7906-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7906-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7906-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c7906-127">See also</span></span>
- [<span data-ttu-id="c7906-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="c7906-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="c7906-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c7906-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="c7906-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c7906-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="c7906-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c7906-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="c7906-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c7906-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="c7906-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c7906-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c7906-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="c7906-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="c7906-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c7906-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="c7906-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="c7906-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c7906-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="c7906-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="c7906-138">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="c7906-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
