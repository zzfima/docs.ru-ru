---
title: Функция FunctionEnter3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: 75a9a7174f105d99e9d1c9b220cfc5bf928d46ec
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866974"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="6861a-102">Функция FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6861a-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="6861a-103">Уведомляет профилировщик о передаче управления в функцию и предоставляет маркер, который может быть передан [методу ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) для получения кадра стека и аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="6861a-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6861a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6861a-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6861a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6861a-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="6861a-106">\[в] идентификатор функции, для которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6861a-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="6861a-107">\[in] непрозрачный маркер, представляющий сведения об определенном кадре стека.</span><span class="sxs-lookup"><span data-stu-id="6861a-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6861a-108">Этот маркер действителен только во время обратного вызова, к которому он передается.</span><span class="sxs-lookup"><span data-stu-id="6861a-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="6861a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6861a-109">Remarks</span></span>  
 <span data-ttu-id="6861a-110">Метод обратного вызова `FunctionEnter3WithInfo` уведомляет профилировщик о вызове функций и позволяет профилировщику использовать [метод ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) для проверки значений аргументов.</span><span class="sxs-lookup"><span data-stu-id="6861a-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="6861a-111">Чтобы получить доступ к сведениям об аргументах, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="6861a-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="6861a-112">Профилировщик может использовать [метод ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий, а затем использовать [метод ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) для регистрации реализации этой функции.</span><span class="sxs-lookup"><span data-stu-id="6861a-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="6861a-113">Функция `FunctionEnter3WithInfo` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="6861a-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="6861a-114">Реализация должна использовать атрибут класса хранения `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="6861a-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="6861a-115">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="6861a-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6861a-116">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="6861a-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6861a-117">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="6861a-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6861a-118">Реализация `FunctionEnter3WithInfo` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6861a-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="6861a-119">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, удобном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="6861a-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6861a-120">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionEnter3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="6861a-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="6861a-121">Функция `FunctionEnter3WithInfo` не должна вызывать управляемый код или вызывать управляемое выделение памяти каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="6861a-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6861a-122">Требования</span><span class="sxs-lookup"><span data-stu-id="6861a-122">Requirements</span></span>  
 <span data-ttu-id="6861a-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6861a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6861a-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="6861a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6861a-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6861a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6861a-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6861a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6861a-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="6861a-127">See also</span></span>

- [<span data-ttu-id="6861a-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="6861a-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="6861a-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="6861a-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="6861a-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="6861a-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="6861a-131">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="6861a-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
