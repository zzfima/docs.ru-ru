---
title: Функция FunctionIDMapper
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175178"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="d351b-102">Функция FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d351b-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="d351b-103">Уведомляет профайлер о том, что данный идентификатор функции может быть перенаправлен в альтернативный идентификатор, который будет использоваться в [FunctionEnter2,](functionenter2-function.md) [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md) для обратных вызовов для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="d351b-104">`FunctionIDMapper` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d351b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d351b-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d351b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d351b-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="d351b-107">\[в» идентификатор функции, который будет remapped.</span><span class="sxs-lookup"><span data-stu-id="d351b-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="d351b-108">\[из указателя на значение, которое профайлер устанавливает, `true` если он хочет получить, `FunctionEnter2` `FunctionLeave2`, и `FunctionTailcall2` обратные вызовы; в противном случае, `false`он устанавливает это значение для .</span><span class="sxs-lookup"><span data-stu-id="d351b-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d351b-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d351b-109">Return Value</span></span>  
 <span data-ttu-id="d351b-110">Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="d351b-111">Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d351b-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="d351b-112">В противном случае значение нулевой доходности приведет к непредсказуемым результатам, включая возможное прекращение процесса.</span><span class="sxs-lookup"><span data-stu-id="d351b-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d351b-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d351b-113">Remarks</span></span>  
 <span data-ttu-id="d351b-114">Функция `FunctionIDMapper` является обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="d351b-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="d351b-115">Он реализован профайлером для переоценки идентификатора функции на другой идентификатор, который является более полезным для профайлера.</span><span class="sxs-lookup"><span data-stu-id="d351b-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="d351b-116">Возвращает `FunctionIDMapper` альтернативный идентификатор, который будет использоваться для любой данной функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="d351b-117">Двигатель исполнения затем выполняет запрос профайлера, передавая этот альтернативный идентификатор, в `clientData` дополнение к `FunctionEnter2` `FunctionLeave2`традиционной `FunctionTailcall2` идентификатор функции, обратно к профилировщику в параметре , и крючки, чтобы определить функцию, для которой крючок вызывается.</span><span class="sxs-lookup"><span data-stu-id="d351b-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="d351b-118">Вы можете использовать метод [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) для `FunctionIDMapper` указания реализации функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="d351b-119">Вы можете `ICorProfilerInfo::SetFunctionIDMapper` позвонить по методу только один раз, и мы рекомендуем вам сделать это в [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="d351b-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="d351b-120">По умолчанию предполагается, что профайлер, который устанавливает COR_PRF_MONITOR_ENTERLEAVE флаг с помощью [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), и который устанавливает крючки через [ICorProfilerInfo::SetEnterLeaveFunctionХукс](icorprofilerinfo-setenterleavefunctionhooks-method.md) или `FunctionTailcall2` [ICorProfilerInfo2::SetEnterLeaveFunctionХикс2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должны получать `FunctionEnter2`, `FunctionLeave2`, и обратные вызовы для каждой функции.</span><span class="sxs-lookup"><span data-stu-id="d351b-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="d351b-121">Тем не менее, `FunctionIDMapper` профайлеры могут осуществлять выборочно избегать получения этих обратных вызовов для определенных функций, установив `pbHookFunction` на `false`.</span><span class="sxs-lookup"><span data-stu-id="d351b-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="d351b-122">Профилеры должны быть терпимыми к случаям, когда несколько потоков профилированного приложения вызывают один и тот же метод/функцию одновременно.</span><span class="sxs-lookup"><span data-stu-id="d351b-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="d351b-123">В таких случаях профайлер `FunctionIDMapper` может получить несколько `FunctionID`обратных вызовов за одно и то же .</span><span class="sxs-lookup"><span data-stu-id="d351b-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="d351b-124">Профайлер должен быть уверен, чтобы вернуть те же значения из этого `FunctionID`обратного вызова, когда он называется несколько раз с тем же .</span><span class="sxs-lookup"><span data-stu-id="d351b-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d351b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d351b-125">Requirements</span></span>  
 <span data-ttu-id="d351b-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d351b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d351b-127">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d351b-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d351b-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d351b-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d351b-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d351b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d351b-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d351b-130">See also</span></span>

- [<span data-ttu-id="d351b-131">Метод SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d351b-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d351b-132">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d351b-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="d351b-133">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="d351b-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="d351b-134">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="d351b-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="d351b-135">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="d351b-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="d351b-136">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="d351b-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
