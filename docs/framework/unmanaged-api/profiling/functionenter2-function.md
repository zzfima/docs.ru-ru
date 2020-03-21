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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177063"
---
# <a name="functionenter2-function"></a><span data-ttu-id="f5a37-102">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="f5a37-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="f5a37-103">Уведомляет профайлера о том, что элемент управления передается функции, и предоставляет информацию о кадровом штабе и аргументах функции.</span><span class="sxs-lookup"><span data-stu-id="f5a37-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="f5a37-104">Эта функция заменяет функцию [FunctionEnter.](functionenter-function.md)</span><span class="sxs-lookup"><span data-stu-id="f5a37-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a37-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5a37-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a37-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5a37-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="f5a37-107">\[в» Идентификатор функции, к которой передается контроль.</span><span class="sxs-lookup"><span data-stu-id="f5a37-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="f5a37-108">\[в идентификаторе remapped функции, который профайлер ранее указал с помощью функции [FunctionIDMapper.](functionidmapper-function.md)</span><span class="sxs-lookup"><span data-stu-id="f5a37-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="f5a37-109">\[в `COR_PRF_FRAME_INFO` значении, которое указывает на информацию о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="f5a37-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="f5a37-110">Профайлер должен рассматривать это как непрозрачную ручку, которая может быть передана обратно в двигатель исполнения в методе [ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)</span><span class="sxs-lookup"><span data-stu-id="f5a37-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="f5a37-111">\[в» указатель на [структуру COR_PRF_FUNCTION_ARGUMENT_INFO,](cor-prf-function-argument-info-structure.md) которая определяет местоположения в памяти аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="f5a37-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="f5a37-112">Для того, чтобы получить `COR_PRF_ENABLE_FUNCTION_ARGS` доступ к информации аргумент, флаг должен быть установлен.</span><span class="sxs-lookup"><span data-stu-id="f5a37-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="f5a37-113">Профайлер может использовать метод [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) для установки флагов событий.</span><span class="sxs-lookup"><span data-stu-id="f5a37-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="f5a37-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5a37-114">Remarks</span></span>  
 <span data-ttu-id="f5a37-115">Значения `func` и `argumentInfo` параметры недействительны после возвращения `FunctionEnter2` функции, поскольку значения могут изменяться или быть уничтожены.</span><span class="sxs-lookup"><span data-stu-id="f5a37-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="f5a37-116">Функция `FunctionEnter2` является обратным вызовом; вы должны реализовать его.</span><span class="sxs-lookup"><span data-stu-id="f5a37-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="f5a37-117">Реализация должна использовать `__declspec``naked`атрибут типа хранения .</span><span class="sxs-lookup"><span data-stu-id="f5a37-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="f5a37-118">Двигатель выполнения не сохраняет регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="f5a37-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="f5a37-119">При входе необходимо сохранить все регистры, которые вы используете, в том числе в блоке плавающей точки (FPU).</span><span class="sxs-lookup"><span data-stu-id="f5a37-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="f5a37-120">На выходе необходимо восстановить стек, выскочив все параметры, которые были проталкиваются абонентом.</span><span class="sxs-lookup"><span data-stu-id="f5a37-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f5a37-121">Реализация не `FunctionEnter2` должна блокироваться, так как это приведет к задержке сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="f5a37-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="f5a37-122">Реализация не должна пытаться выбросить мусор, поскольку стек может быть не в удобном для сбора мусора состоянии.</span><span class="sxs-lookup"><span data-stu-id="f5a37-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f5a37-123">При попытке сбора мусора время выполнения `FunctionEnter2` будет блокироваться до возвращения.</span><span class="sxs-lookup"><span data-stu-id="f5a37-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="f5a37-124">Кроме того, `FunctionEnter2` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="f5a37-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a37-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f5a37-125">Requirements</span></span>  
 <span data-ttu-id="f5a37-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a37-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a37-127">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f5a37-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f5a37-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a37-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a37-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a37-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a37-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5a37-130">See also</span></span>

- [<span data-ttu-id="f5a37-131">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="f5a37-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="f5a37-132">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="f5a37-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="f5a37-133">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="f5a37-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="f5a37-134">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="f5a37-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
