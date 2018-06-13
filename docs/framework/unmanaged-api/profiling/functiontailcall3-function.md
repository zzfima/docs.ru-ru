---
title: Функция FunctionTailcall3
ms.date: 03/30/2017
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82d718c6f6aee36f3a916eb7f9b9a1e0b3b46cb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452472"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="15db7-102">Функция FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="15db7-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="15db7-103">Уведомляет профилировщик о том, что текущей выполняемой функции собирается выполнить вызов с префиксом tail в другую функцию.</span><span class="sxs-lookup"><span data-stu-id="15db7-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15db7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15db7-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15db7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15db7-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="15db7-106">[in] Идентификатор текущей выполняемой функции, внесет с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="15db7-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15db7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="15db7-107">Remarks</span></span>  
 <span data-ttu-id="15db7-108">`FunctionTailcall3` Функция обратного вызова Уведомляет профилировщик при вызове функций.</span><span class="sxs-lookup"><span data-stu-id="15db7-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="15db7-109">Используйте [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="15db7-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="15db7-110">`FunctionTailcall3` Функция является обратным вызовом, необходимо произвести его.</span><span class="sxs-lookup"><span data-stu-id="15db7-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="15db7-111">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="15db7-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="15db7-112">Перед вызовом этой функции ядро выполнения не сохраняет значения регистров.</span><span class="sxs-lookup"><span data-stu-id="15db7-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="15db7-113">При входе необходимо сохранить все используемые регистры, включая те, в единицах измерения с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="15db7-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="15db7-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, переведенных вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="15db7-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="15db7-115">Реализация `FunctionTailcall3` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="15db7-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="15db7-116">Реализация не должны предпринимать попытки сбора мусора, так как стек может находиться в состоянии понятного имени сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="15db7-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="15db7-117">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionTailcall3` возвращает.</span><span class="sxs-lookup"><span data-stu-id="15db7-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="15db7-118">`FunctionTailcall3` Функция не должна вызывать управляемый код или вызвать распределения управляемой памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="15db7-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15db7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="15db7-119">Requirements</span></span>  
 <span data-ttu-id="15db7-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15db7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15db7-121">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="15db7-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="15db7-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15db7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15db7-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15db7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15db7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="15db7-124">See Also</span></span>  
 [<span data-ttu-id="15db7-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="15db7-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="15db7-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="15db7-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="15db7-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="15db7-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="15db7-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="15db7-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="15db7-129">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="15db7-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="15db7-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="15db7-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="15db7-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="15db7-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="15db7-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="15db7-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="15db7-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="15db7-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="15db7-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="15db7-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
