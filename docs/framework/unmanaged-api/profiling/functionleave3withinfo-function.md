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
ms.openlocfilehash: a62f402fbfae6188ab0423ea7a55a4dfc6cb4112
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427399"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="a9792-102">Функция FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9792-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="a9792-103">Уведомляет профилировщик о том, что управление возвращается из функции, и предоставляет маркер, который может быть передан [методу ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для получения кадра стека и возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="a9792-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9792-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9792-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9792-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9792-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="a9792-106">окне Идентификатор функции, из которой возвращается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a9792-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a9792-107">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="a9792-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a9792-108">Этот маркер действителен только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="a9792-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9792-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="a9792-109">Remarks</span></span>  
 <span data-ttu-id="a9792-110">Метод обратного вызова `FunctionLeave3WithInfo` уведомляет профилировщик о вызове функций и позволяет профилировщику использовать [метод ICorProfilerInfo3:: GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) для проверки возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="a9792-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="a9792-111">Чтобы получить доступ к сведениям о возвращаемом значении, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="a9792-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="a9792-112">Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="a9792-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a9792-113">Функция `FunctionLeave3WithInfo` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="a9792-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="a9792-114">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="a9792-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="a9792-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="a9792-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a9792-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="a9792-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a9792-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="a9792-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a9792-118">Реализация `FunctionLeave3WithInfo` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a9792-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="a9792-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="a9792-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a9792-120">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="a9792-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="a9792-121">Функция `FunctionLeave3WithInfo` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="a9792-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9792-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a9792-122">Requirements</span></span>  
 <span data-ttu-id="a9792-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9792-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9792-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="a9792-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a9792-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9792-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9792-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9792-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9792-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a9792-127">See also</span></span>

- [<span data-ttu-id="a9792-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="a9792-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="a9792-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="a9792-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="a9792-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a9792-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="a9792-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="a9792-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="a9792-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9792-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="a9792-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9792-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="a9792-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="a9792-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="a9792-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="a9792-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="a9792-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="a9792-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="a9792-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="a9792-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="a9792-138">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="a9792-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
