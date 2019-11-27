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
ms.openlocfilehash: 104a6c3c42c310513040cb45db7f51ffe729c19d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427438"
---
# <a name="functionleave3-function"></a><span data-ttu-id="3b25a-102">Функция FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="3b25a-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="3b25a-103">Уведомляет профилировщик о том, что управление возвращается из функции.</span><span class="sxs-lookup"><span data-stu-id="3b25a-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b25a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b25a-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b25a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b25a-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="3b25a-106">окне Идентификатор функции, из которой возвращается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="3b25a-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b25a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b25a-107">Remarks</span></span>  
 <span data-ttu-id="3b25a-108">Функция обратного вызова `FunctionLeave3` уведомляет профилировщик о вызове функций, но не поддерживает проверку возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="3b25a-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="3b25a-109">Чтобы зарегистрировать реализацию этой функции, используйте [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b25a-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="3b25a-110">Функция `FunctionLeave3` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="3b25a-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="3b25a-111">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="3b25a-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="3b25a-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="3b25a-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="3b25a-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="3b25a-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="3b25a-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="3b25a-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="3b25a-115">Реализация `FunctionLeave3` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3b25a-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="3b25a-116">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3b25a-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="3b25a-117">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave3`.</span><span class="sxs-lookup"><span data-stu-id="3b25a-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="3b25a-118">Функция `FunctionLeave3` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="3b25a-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b25a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3b25a-119">Requirements</span></span>  
 <span data-ttu-id="3b25a-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b25a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b25a-121">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="3b25a-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3b25a-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b25a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b25a-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b25a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b25a-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b25a-124">See also</span></span>

- [<span data-ttu-id="3b25a-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="3b25a-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="3b25a-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="3b25a-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="3b25a-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b25a-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="3b25a-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b25a-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="3b25a-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b25a-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="3b25a-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="3b25a-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="3b25a-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="3b25a-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="3b25a-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="3b25a-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="3b25a-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="3b25a-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="3b25a-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="3b25a-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
