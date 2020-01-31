---
title: Функция FunctionLeave2
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: 0b1ecd1266528f8a08ef114de2f111dd0f71ca8b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866935"
---
# <a name="functionleave2-function"></a><span data-ttu-id="c2e08-102">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="c2e08-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="c2e08-103">Уведомляет профилировщик о том, что функция собирается вернуться к вызывающему объекту, и предоставляет сведения о кадре стека и возвращаемом значении функции.</span><span class="sxs-lookup"><span data-stu-id="c2e08-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e08-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2e08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2e08-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="c2e08-106">\[in] Идентификатор возвращаемой функции.</span><span class="sxs-lookup"><span data-stu-id="c2e08-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="c2e08-107">\[in] идентификатор повторно сопоставленной функции, который профилировщик ранее указал с помощью функции [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c2e08-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="c2e08-108">\[in] `COR_PRF_FRAME_INFO` значение, указывающее на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="c2e08-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="c2e08-109">Профилировщик должен рассматривать это как непрозрачный маркер, который можно передать обратно в подсистему выполнения метода [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c2e08-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="c2e08-110">\[в] указатель на структуру [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) , указывающую расположение в памяти возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="c2e08-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="c2e08-111">Чтобы получить доступ к сведениям о возвращаемом значении, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="c2e08-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="c2e08-112">Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.</span><span class="sxs-lookup"><span data-stu-id="c2e08-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="c2e08-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="c2e08-113">Remarks</span></span>  
 <span data-ttu-id="c2e08-114">Значения параметров `func` и `retvalRange` недопустимы после возврата функции `FunctionLeave2`, поскольку значения могут измениться или быть уничтожены.</span><span class="sxs-lookup"><span data-stu-id="c2e08-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="c2e08-115">Функция `FunctionLeave2` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="c2e08-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="c2e08-116">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="c2e08-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="c2e08-117">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="c2e08-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="c2e08-118">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="c2e08-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="c2e08-119">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="c2e08-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c2e08-120">Реализация `FunctionLeave2` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c2e08-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="c2e08-121">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c2e08-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c2e08-122">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionLeave2`.</span><span class="sxs-lookup"><span data-stu-id="c2e08-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="c2e08-123">Кроме того, функция `FunctionLeave2` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="c2e08-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e08-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c2e08-124">Requirements</span></span>  
 <span data-ttu-id="c2e08-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e08-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e08-126">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="c2e08-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c2e08-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2e08-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2e08-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e08-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e08-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="c2e08-129">See also</span></span>

- [<span data-ttu-id="c2e08-130">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="c2e08-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="c2e08-131">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="c2e08-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="c2e08-132">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="c2e08-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="c2e08-133">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="c2e08-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
