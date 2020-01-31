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
ms.openlocfilehash: 3bedb2c5f55f608b1153272437c0f55b730c2dfc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866860"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="dc6a6-102">Функция FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="dc6a6-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="dc6a6-103">Уведомляет профилировщик о том, что выполняемая в данный момент функция собирается выполнить вызов другой функции с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc6a6-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc6a6-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="dc6a6-106">\[в] идентификатор выполняемой в данный момент функции, которая собирается выполнить вызов с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc6a6-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="dc6a6-107">Remarks</span></span>  
 <span data-ttu-id="dc6a6-108">Функция обратного вызова `FunctionTailcall3` уведомляет профилировщик о вызове функций.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="dc6a6-109">Чтобы зарегистрировать реализацию этой функции, используйте [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6a6-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="dc6a6-110">Функция `FunctionTailcall3` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="dc6a6-111">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="dc6a6-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="dc6a6-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="dc6a6-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="dc6a6-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="dc6a6-115">Реализация `FunctionTailcall3` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="dc6a6-116">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="dc6a6-117">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionTailcall3`.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="dc6a6-118">Функция `FunctionTailcall3` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6a6-119">Требования</span><span class="sxs-lookup"><span data-stu-id="dc6a6-119">Requirements</span></span>  
 <span data-ttu-id="dc6a6-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6a6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6a6-121">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="dc6a6-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="dc6a6-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6a6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6a6-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6a6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6a6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="dc6a6-124">See also</span></span>

- [<span data-ttu-id="dc6a6-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="dc6a6-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="dc6a6-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="dc6a6-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="dc6a6-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dc6a6-127">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="dc6a6-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dc6a6-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="dc6a6-129">Функция FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dc6a6-129">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="dc6a6-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="dc6a6-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="dc6a6-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="dc6a6-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="dc6a6-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="dc6a6-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="dc6a6-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="dc6a6-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="dc6a6-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="dc6a6-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
