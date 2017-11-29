---
title: "Функция FunctionLeave2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave2
helpviewer_keywords: FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c2dd85e23a54a20920e30e22bc91f88a813be39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave2-function"></a><span data-ttu-id="929a4-102">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="929a4-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="929a4-103">Уведомляет профилировщик, функция вернет вызывающему объекту, а также сведения о стека фрейма и функция возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="929a4-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="929a4-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="929a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="929a4-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="929a4-106">[in] Идентификатор функции, которая возвращает.</span><span class="sxs-lookup"><span data-stu-id="929a4-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="929a4-107">[in] Идентификатор повторно сопоставленной функции, который ранее указанного профилировщик с помощью [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="929a4-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="929a4-108">[in] Объект `COR_PRF_FRAME_INFO` значение, которое указывает на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="929a4-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="929a4-109">Профилировщик должен интерпретировать его как непрозрачный дескриптор, который может быть передан обратно в ядро выполнения в [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="929a4-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="929a4-110">[in] Указатель на [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структура, которая задает расположение возвращаемое значение функции в памяти.</span><span class="sxs-lookup"><span data-stu-id="929a4-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="929a4-111">Чтобы получить доступ к информации возвращаемое значение `COR_PRF_ENABLE_FUNCTION_RETVAL` должен быть установлен флаг.</span><span class="sxs-lookup"><span data-stu-id="929a4-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="929a4-112">Можно использовать профилировщик [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) метод, чтобы задать флаги событий.</span><span class="sxs-lookup"><span data-stu-id="929a4-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="929a4-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="929a4-113">Remarks</span></span>  
 <span data-ttu-id="929a4-114">Значения `func` и `retvalRange` параметры не допускаются после `FunctionLeave2` функция возвращает, так как значения, могут быть изменены или удалены.</span><span class="sxs-lookup"><span data-stu-id="929a4-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="929a4-115">`FunctionLeave2` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="929a4-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="929a4-116">В реализации должен использоваться `__declspec`(`naked`) атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="929a4-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="929a4-117">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="929a4-117">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="929a4-118">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="929a4-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="929a4-119">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="929a4-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="929a4-120">Реализация `FunctionLeave2` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="929a4-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="929a4-121">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="929a4-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="929a4-122">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave2` возвращает.</span><span class="sxs-lookup"><span data-stu-id="929a4-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="929a4-123">Кроме того `FunctionLeave2` функции не следует вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="929a4-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929a4-124">Требования</span><span class="sxs-lookup"><span data-stu-id="929a4-124">Requirements</span></span>  
 <span data-ttu-id="929a4-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="929a4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929a4-126">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="929a4-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="929a4-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="929a4-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="929a4-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929a4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929a4-129">См. также</span><span class="sxs-lookup"><span data-stu-id="929a4-129">See Also</span></span>  
 [<span data-ttu-id="929a4-130">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="929a4-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="929a4-131">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="929a4-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="929a4-132">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="929a4-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="929a4-133">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="929a4-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
