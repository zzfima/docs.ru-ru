---
title: Функция FunctionEnter2
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 6cd35c180b8a322b3402b050c6d6840073010b1f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866987"
---
# <a name="functionenter2-function"></a><span data-ttu-id="04055-102">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="04055-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="04055-103">Уведомляет профилировщик о передаче управления в функцию и предоставляет сведения о кадре стека и аргументах функции.</span><span class="sxs-lookup"><span data-stu-id="04055-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="04055-104">Эта функция заменяет функцию [FunctionEnter](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="04055-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04055-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04055-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04055-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="04055-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="04055-107">\[в] идентификатор функции, для которой передается элемент управления.</span><span class="sxs-lookup"><span data-stu-id="04055-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="04055-108">\[in] идентификатор повторно сопоставленной функции, которую профилировщик указал ранее с помощью функции [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="04055-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="04055-109">\[in] `COR_PRF_FRAME_INFO` значение, указывающее на сведения о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="04055-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="04055-110">Профилировщик должен рассматривать это как непрозрачный маркер, который можно передать обратно в подсистему выполнения метода [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="04055-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="04055-111">\[в] указатель на структуру [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) , указывающую расположения в памяти аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="04055-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="04055-112">Чтобы получить доступ к сведениям об аргументах, необходимо установить флаг `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="04055-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="04055-113">Профилировщик может использовать метод [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.</span><span class="sxs-lookup"><span data-stu-id="04055-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="04055-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="04055-114">Remarks</span></span>  
 <span data-ttu-id="04055-115">Значения параметров `func` и `argumentInfo` недопустимы после возврата функции `FunctionEnter2`, поскольку значения могут измениться или быть уничтожены.</span><span class="sxs-lookup"><span data-stu-id="04055-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="04055-116">Функция `FunctionEnter2` является обратным вызовом. его необходимо реализовать.</span><span class="sxs-lookup"><span data-stu-id="04055-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="04055-117">Реализация должна использовать атрибут класса хранения `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="04055-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="04055-118">Подсистема выполнения не сохраняет никакие регистры перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="04055-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="04055-119">Во время записи необходимо сохранить все используемые регистры, включая те, которые находятся в блоке с плавающей запятой (FPU).</span><span class="sxs-lookup"><span data-stu-id="04055-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="04055-120">При выходе необходимо восстановить стек, выключив все параметры, которые были переданы его вызывающим.</span><span class="sxs-lookup"><span data-stu-id="04055-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="04055-121">Реализация `FunctionEnter2` не должна блокироваться, так как она приведет к задержке сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="04055-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="04055-122">Реализация не должна пытаться выполнить сборку мусора, так как стек может не находиться в состоянии, понятном для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="04055-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="04055-123">Если выполняется сборка мусора, среда выполнения блокируется до тех пор, пока не будет возвращено `FunctionEnter2`.</span><span class="sxs-lookup"><span data-stu-id="04055-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="04055-124">Кроме того, функция `FunctionEnter2` не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="04055-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04055-125">Требования</span><span class="sxs-lookup"><span data-stu-id="04055-125">Requirements</span></span>  
 <span data-ttu-id="04055-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04055-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04055-127">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="04055-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="04055-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04055-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04055-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04055-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04055-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="04055-130">See also</span></span>

- [<span data-ttu-id="04055-131">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="04055-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="04055-132">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="04055-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="04055-133">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="04055-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="04055-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="04055-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
