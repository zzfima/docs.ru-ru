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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4352d006c95a5b85341625220e6c7e62a86b482a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59178091"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="37117-102">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="37117-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="37117-103">Уведомляет профилировщик, текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию и предоставляет маркер, который может быть передан [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для извлечения кадр стека.</span><span class="sxs-lookup"><span data-stu-id="37117-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37117-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37117-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37117-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37117-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="37117-106">[in] Идентификатор текущей выполняемой функции, который собираетесь сделать с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="37117-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="37117-107">[in] Непрозрачный дескриптор, представляющий сведения об указанном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="37117-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="37117-108">Этот дескриптор допустим только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="37117-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37117-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="37117-109">Remarks</span></span>  
 <span data-ttu-id="37117-110">`FunctionTailcall3WithInfo` Метод обратного вызова Уведомляет профилировщик, как функции, называются, а также позволяет профилировщику использовать [метод ICorProfilerInfo3::GetFunctionTailcall3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) для проверки кадров стека.</span><span class="sxs-lookup"><span data-stu-id="37117-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="37117-111">Чтобы получить доступ к сведения о кадре стека, `COR_PRF_ENABLE_FRAME_INFO` флаг должно иметь значение.</span><span class="sxs-lookup"><span data-stu-id="37117-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="37117-112">Можно использовать профилировщик [метод ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) установить флаги событий, а затем использовать [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации вашей Реализация этой функции.</span><span class="sxs-lookup"><span data-stu-id="37117-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="37117-113">`FunctionTailcall3WithInfo` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="37117-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="37117-114">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="37117-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="37117-115">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="37117-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="37117-116">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="37117-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="37117-117">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="37117-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="37117-118">Реализация `FunctionTailcall3WithInfo` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="37117-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="37117-119">Реализация не должны в сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="37117-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="37117-120">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall3WithInfo` возвращает.</span><span class="sxs-lookup"><span data-stu-id="37117-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="37117-121">Кроме того функция FunctionTailcall3WithInfo не должен вызов управляемого кода или инициировать распределение управляемой памяти любым способом.</span><span class="sxs-lookup"><span data-stu-id="37117-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37117-122">Требования</span><span class="sxs-lookup"><span data-stu-id="37117-122">Requirements</span></span>  
 <span data-ttu-id="37117-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37117-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37117-124">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="37117-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="37117-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37117-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37117-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37117-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37117-127">См. также</span><span class="sxs-lookup"><span data-stu-id="37117-127">See also</span></span>

- [<span data-ttu-id="37117-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="37117-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="37117-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="37117-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="37117-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="37117-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="37117-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="37117-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="37117-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="37117-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="37117-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="37117-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="37117-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="37117-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="37117-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="37117-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="37117-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="37117-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="37117-137">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="37117-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
