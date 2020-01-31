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
ms.openlocfilehash: f7a945fb7ef10f995be2d779a88b98bbce2fdfb3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866847"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="6fccf-102">Функция FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6fccf-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="6fccf-103">Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который может быть передан [методу ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="6fccf-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fccf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fccf-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fccf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6fccf-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="6fccf-106">\[в] идентификатор функции, из которой возвращается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6fccf-106">\[in] The identifier of the function from which control is returned.</span></span>

- `eltInfo`

  <span data-ttu-id="6fccf-107">\[in] непрозрачный маркер, представляющий сведения об определенном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="6fccf-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6fccf-108">Этот маркер действителен только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="6fccf-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fccf-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6fccf-109">Remarks</span></span>  
 <span data-ttu-id="6fccf-110">Метод обратного вызова `FunctionLeave3WithInfo` уведомляет профилировщик о вызове функций и позволяет профилировщику использовать [метод ICorProfilerInfo3:: GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md) для проверки возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="6fccf-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="6fccf-111">Чтобы получить доступ к сведениям о возвращаемом значении, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="6fccf-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="6fccf-112">Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="6fccf-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6fccf-113">Функция `FunctionLeave3WithInfo` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="6fccf-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="6fccf-114">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="6fccf-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="6fccf-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="6fccf-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6fccf-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="6fccf-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6fccf-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="6fccf-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6fccf-118">Реализация `FunctionLeave3WithInfo` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6fccf-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="6fccf-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6fccf-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6fccf-120">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="6fccf-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="6fccf-121">Функция `FunctionLeave3WithInfo` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="6fccf-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fccf-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6fccf-122">Requirements</span></span>  
 <span data-ttu-id="6fccf-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fccf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fccf-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="6fccf-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6fccf-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fccf-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fccf-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fccf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fccf-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6fccf-127">See also</span></span>

- [<span data-ttu-id="6fccf-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="6fccf-128">GetFunctionLeave3Info</span></span>](icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="6fccf-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6fccf-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="6fccf-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6fccf-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="6fccf-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="6fccf-131">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="6fccf-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6fccf-132">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="6fccf-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6fccf-133">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="6fccf-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="6fccf-134">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="6fccf-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6fccf-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="6fccf-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="6fccf-136">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="6fccf-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="6fccf-137">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="6fccf-138">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="6fccf-138">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
