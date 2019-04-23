---
title: Функция FunctionLeave3
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b31c3045b021bd3b00d2b2e42bf7a118110305b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099892"
---
# <a name="functionleave3-function"></a><span data-ttu-id="4ce4f-102">Функция FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="4ce4f-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="4ce4f-103">Уведомляет профилировщик, что элемент управления возвращается из функции.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ce4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ce4f-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ce4f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ce4f-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="4ce4f-106">[in] Идентификатор функции, из которого возвращается.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ce4f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ce4f-107">Remarks</span></span>  
 <span data-ttu-id="4ce4f-108">`FunctionLeave3` Функцию обратного вызова Уведомляет профилировщик при вызове функции, но не поддерживает проверку возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="4ce4f-109">Используйте [метод ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) для регистрации вашей реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="4ce4f-110">`FunctionLeave3` Функция является обратным вызовом; это необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="4ce4f-111">В реализации должен использоваться `__declspec(naked)` атрибут класса хранения.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="4ce4f-112">Ядро выполнения не сохраняет значения регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="4ce4f-113">При входе необходимо сохранить все регистры, которые вы используете, включая те, в единицах с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="4ce4f-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="4ce4f-114">При выходе необходимо восстановить стек путем выталкивания из всех параметров, которые были отправлены вызывающим кодом.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="4ce4f-115">Реализация `FunctionLeave3` не должен блокироваться, поскольку это приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="4ce4f-116">Реализация не должны в сбор мусора, так как стек может находиться в состоянии коллекции с поддержкой сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="4ce4f-117">При попытке сбора мусора, среда выполнения будет блокироваться до `FunctionLeave3` возвращает.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="4ce4f-118">`FunctionLeave3` Функция не должна вызов управляемого кода или инициировать распределение управляемой памяти любым способом.</span><span class="sxs-lookup"><span data-stu-id="4ce4f-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ce4f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="4ce4f-119">Requirements</span></span>  
 <span data-ttu-id="4ce4f-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ce4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ce4f-121">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="4ce4f-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4ce4f-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ce4f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ce4f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ce4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce4f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="4ce4f-124">See also</span></span>

- [<span data-ttu-id="4ce4f-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="4ce4f-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="4ce4f-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="4ce4f-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="4ce4f-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4ce4f-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="4ce4f-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4ce4f-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="4ce4f-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4ce4f-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="4ce4f-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="4ce4f-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="4ce4f-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="4ce4f-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="4ce4f-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4ce4f-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4ce4f-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4ce4f-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="4ce4f-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="4ce4f-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
