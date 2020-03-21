---
title: Функция FunctionTailcall2
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175191"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="b2a03-102">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="b2a03-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="b2a03-103">Уведомляет профайлера о том, что функция выполнения в настоящее время собирается выполнить хвостовой вызов другой функции, и предоставляет информацию о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="b2a03-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2a03-104">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2a03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2a03-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="b2a03-106">\[в» идентификатор в настоящее время выполнения функции, которая собирается сделать хвост вызова.</span><span class="sxs-lookup"><span data-stu-id="b2a03-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="b2a03-107">\[в» Идентификатор функции remapped, который профайлер ранее определил через [FunctionIDMapper](functionidmapper-function.md), в настоящее время исполняя функцию которая около сделать звонок кабеля.</span><span class="sxs-lookup"><span data-stu-id="b2a03-107">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="b2a03-108">\[в `COR_PRF_FRAME_INFO` значении, которое указывает на информацию о кадре стека.</span><span class="sxs-lookup"><span data-stu-id="b2a03-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="b2a03-109">Профайлер должен рассматривать это как непрозрачную ручку, которая может быть передана обратно в двигатель исполнения в методе [ICorProfilerInfo2::GetFunctionInfo2.](icorprofilerinfo2-getfunctioninfo2-method.md)</span><span class="sxs-lookup"><span data-stu-id="b2a03-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2a03-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b2a03-110">Remarks</span></span>  
 <span data-ttu-id="b2a03-111">Целевая функция хвостового вызова будет использовать текущую рамку стека и вернется непосредственно к вызывающему функции, сделавшейней хвостовой вызов.</span><span class="sxs-lookup"><span data-stu-id="b2a03-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="b2a03-112">Это означает, что обратный вызов [FunctionLeave2](functionleave2-function.md) не будет выдан для функции, которая является целью хвостового вызова.</span><span class="sxs-lookup"><span data-stu-id="b2a03-112">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="b2a03-113">Значение `func` параметра не действителен `FunctionTailcall2` после возврата функции, поскольку значение может измениться или быть уничтожено.</span><span class="sxs-lookup"><span data-stu-id="b2a03-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="b2a03-114">Функция `FunctionTailcall2` является обратным вызовом; вы должны реализовать его.</span><span class="sxs-lookup"><span data-stu-id="b2a03-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="b2a03-115">Реализация должна использовать `__declspec``naked`атрибут типа хранения .</span><span class="sxs-lookup"><span data-stu-id="b2a03-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="b2a03-116">Двигатель выполнения не сохраняет регистров перед вызовом этой функции.</span><span class="sxs-lookup"><span data-stu-id="b2a03-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="b2a03-117">При входе необходимо сохранить все регистры, которые вы используете, в том числе в блоке плавающей точки (FPU).</span><span class="sxs-lookup"><span data-stu-id="b2a03-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="b2a03-118">На выходе необходимо восстановить стек, выскочив все параметры, которые были проталкиваются абонентом.</span><span class="sxs-lookup"><span data-stu-id="b2a03-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="b2a03-119">Реализация не `FunctionTailcall2` должна блокироваться, так как это приведет к задержке сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="b2a03-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="b2a03-120">Реализация не должна пытаться выбросить мусор, поскольку стек может быть не в удобном для сбора мусора состоянии.</span><span class="sxs-lookup"><span data-stu-id="b2a03-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="b2a03-121">При попытке сбора мусора время выполнения `FunctionTailcall2` будет блокироваться до возвращения.</span><span class="sxs-lookup"><span data-stu-id="b2a03-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="b2a03-122">Кроме того, `FunctionTailcall2` функция не должна вызывать управляемый код или каким-либо образом вызывать управляемое распределение памяти.</span><span class="sxs-lookup"><span data-stu-id="b2a03-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a03-123">Требования</span><span class="sxs-lookup"><span data-stu-id="b2a03-123">Requirements</span></span>  
 <span data-ttu-id="b2a03-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2a03-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a03-125">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b2a03-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b2a03-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a03-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2a03-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a03-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a03-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b2a03-128">See also</span></span>

- [<span data-ttu-id="b2a03-129">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="b2a03-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="b2a03-130">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="b2a03-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="b2a03-131">Метод SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="b2a03-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="b2a03-132">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="b2a03-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
