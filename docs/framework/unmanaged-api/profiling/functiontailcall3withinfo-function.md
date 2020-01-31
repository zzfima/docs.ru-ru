---
title: Функция FunctionTailcall3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: 0aa43954c3e10d04524bf976d0dd3b29d2bc724c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866834"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="10e6d-102">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="10e6d-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="10e6d-103">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail, и предоставляет маркер, который может быть передан [методу ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) для получения кадра стека.</span><span class="sxs-lookup"><span data-stu-id="10e6d-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10e6d-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10e6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10e6d-105">Parameters</span></span>  

- `functionIDOrClientID`

  <span data-ttu-id="10e6d-106">\[в] идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="10e6d-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `eltInfo`

  <span data-ttu-id="10e6d-107">\[in] непрозрачный маркер, представляющий сведения об определенном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="10e6d-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="10e6d-108">Этот маркер действителен только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="10e6d-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="10e6d-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="10e6d-109">Remarks</span></span>  
 <span data-ttu-id="10e6d-110">Метод обратного вызова `FunctionTailcall3WithInfo` уведомляет профилировщик о вызове функций и позволяет профилировщику использовать [метод ICorProfilerInfo3:: GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md) для проверки кадра стека.</span><span class="sxs-lookup"><span data-stu-id="10e6d-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="10e6d-111">Чтобы получить доступ к сведениям о кадрах стека, необходимо установить флаг `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="10e6d-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="10e6d-112">Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="10e6d-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="10e6d-113">Функция `FunctionTailcall3WithInfo` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="10e6d-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="10e6d-114">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="10e6d-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="10e6d-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="10e6d-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="10e6d-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="10e6d-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="10e6d-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="10e6d-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="10e6d-118">Реализация `FunctionTailcall3WithInfo` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="10e6d-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="10e6d-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="10e6d-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="10e6d-120">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="10e6d-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="10e6d-121">Кроме того, функция FunctionTailcall3WithInfo не должна вызывать управляемый код или каким-либо образом вызывать управляемое выделение памяти.</span><span class="sxs-lookup"><span data-stu-id="10e6d-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e6d-122">Требования</span><span class="sxs-lookup"><span data-stu-id="10e6d-122">Requirements</span></span>  
 <span data-ttu-id="10e6d-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e6d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e6d-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="10e6d-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="10e6d-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e6d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e6d-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e6d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e6d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="10e6d-127">See also</span></span>

- [<span data-ttu-id="10e6d-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="10e6d-128">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="10e6d-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="10e6d-129">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="10e6d-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="10e6d-130">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="10e6d-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="10e6d-131">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="10e6d-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="10e6d-132">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="10e6d-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="10e6d-133">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="10e6d-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="10e6d-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="10e6d-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="10e6d-135">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="10e6d-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="10e6d-136">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="10e6d-137">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="10e6d-137">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
