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
ms.openlocfilehash: 32d86f19e9c50694c7d113195e6967645b710666
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866873"
---
# <a name="functionleave3-function"></a><span data-ttu-id="bde05-102">Функция FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="bde05-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="bde05-103">Уведомляет профилировщик о том, что управление возвращается из функции.</span><span class="sxs-lookup"><span data-stu-id="bde05-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bde05-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bde05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bde05-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="bde05-106">\[в] идентификатор функции, из которой возвращается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bde05-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="bde05-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="bde05-107">Remarks</span></span>  
 <span data-ttu-id="bde05-108">Функция обратного вызова `FunctionLeave3` уведомляет профилировщик о вызове функций, но не поддерживает проверку возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="bde05-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="bde05-109">Чтобы зарегистрировать реализацию этой функции, используйте [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bde05-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="bde05-110">Функция `FunctionLeave3` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="bde05-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="bde05-111">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="bde05-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="bde05-112">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="bde05-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="bde05-113">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="bde05-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="bde05-114">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="bde05-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="bde05-115">Реализация `FunctionLeave3` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bde05-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="bde05-116">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bde05-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="bde05-117">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave3`.</span><span class="sxs-lookup"><span data-stu-id="bde05-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="bde05-118">Функция `FunctionLeave3` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="bde05-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bde05-119">Требования</span><span class="sxs-lookup"><span data-stu-id="bde05-119">Requirements</span></span>  
 <span data-ttu-id="bde05-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bde05-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bde05-121">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="bde05-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="bde05-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bde05-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bde05-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bde05-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde05-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="bde05-124">See also</span></span>

- [<span data-ttu-id="bde05-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="bde05-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="bde05-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="bde05-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="bde05-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bde05-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="bde05-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bde05-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="bde05-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bde05-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="bde05-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="bde05-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="bde05-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bde05-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="bde05-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="bde05-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="bde05-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="bde05-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="bde05-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="bde05-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
