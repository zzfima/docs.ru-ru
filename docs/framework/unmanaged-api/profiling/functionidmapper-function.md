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
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440706"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="d36a8-102">Функция FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d36a8-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="d36a8-103">Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d36a8-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="d36a8-104">`FunctionIDMapper` также позволяет профилировщику указывать, хотят ли они получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="d36a8-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d36a8-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d36a8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d36a8-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="d36a8-107">[in] Идентификатор функции для повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="d36a8-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="d36a8-108">заполняет Указатель на значение, которое задается профилировщику для `true`, если требуется получать обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2`; в противном случае это значение задается как `false`.</span><span class="sxs-lookup"><span data-stu-id="d36a8-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d36a8-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d36a8-109">Return Value</span></span>  
 <span data-ttu-id="d36a8-110">Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции.</span><span class="sxs-lookup"><span data-stu-id="d36a8-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="d36a8-111">Это возвращаемое значение не может быть значением null, если указатель `false` возвращает значение `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="d36a8-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="d36a8-112">В противном случае возвращаемое значение null приведет к непредсказуемым результатам, включая, возможно, остановку процесса.</span><span class="sxs-lookup"><span data-stu-id="d36a8-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d36a8-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="d36a8-113">Remarks</span></span>  
 <span data-ttu-id="d36a8-114">Функция `FunctionIDMapper` является обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="d36a8-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="d36a8-115">Он реализуется профилировщиком для повторного сопоставления идентификатора функции с другим идентификатором, который более удобен для профилировщика.</span><span class="sxs-lookup"><span data-stu-id="d36a8-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="d36a8-116">`FunctionIDMapper` возвращает альтернативный идентификатор, используемый для любой заданной функции.</span><span class="sxs-lookup"><span data-stu-id="d36a8-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="d36a8-117">Затем подсистема выполнения обрабатывает запрос профилировщика, передавая этот альтернативный идентификатор, помимо традиционного идентификатора функции, обратно в профилировщик в параметре `clientData` обработчиков `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для идентификации функции, для которой вызывается обработчик.</span><span class="sxs-lookup"><span data-stu-id="d36a8-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="d36a8-118">Для указания реализации функции `FunctionIDMapper` можно использовать метод [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d36a8-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="d36a8-119">Метод `ICorProfilerInfo::SetFunctionIDMapper` можно вызвать только один раз, и мы рекомендуем сделать это в обратном вызове [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d36a8-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="d36a8-120">По умолчанию предполагается, что профилировщик, устанавливающий флаг COR_PRF_MONITOR_ENTERLEAVE, с помощью [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), который устанавливает перехватчики через [ICorProfilerInfo:: сетентерлеавефунктионхукс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) или [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должен получить обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для каждой функции.</span><span class="sxs-lookup"><span data-stu-id="d36a8-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="d36a8-121">Однако профилировщики могут реализовать `FunctionIDMapper`, чтобы выборочно избежать получения этих обратных вызовов для определенных функций, установив для `pbHookFunction` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d36a8-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="d36a8-122">Профилировщики должны быть нечувствительными к случаям, когда несколько потоков профилированного приложения вызывают один и тот же метод или функцию одновременно.</span><span class="sxs-lookup"><span data-stu-id="d36a8-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="d36a8-123">В таких случаях профилировщик может получить несколько `FunctionIDMapper`ных обратных вызовов для одного и того же `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="d36a8-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="d36a8-124">Профилировщик должен быть уверенным в том, чтобы возвращать те же значения из этого обратного вызова, когда он вызывается несколько раз с одним и тем же `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="d36a8-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36a8-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d36a8-125">Requirements</span></span>  
 <span data-ttu-id="d36a8-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d36a8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36a8-127">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="d36a8-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d36a8-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d36a8-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d36a8-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36a8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36a8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d36a8-130">See also</span></span>

- [<span data-ttu-id="d36a8-131">Метод SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="d36a8-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d36a8-132">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="d36a8-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [<span data-ttu-id="d36a8-133">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="d36a8-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d36a8-134">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="d36a8-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d36a8-135">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="d36a8-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="d36a8-136">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="d36a8-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
