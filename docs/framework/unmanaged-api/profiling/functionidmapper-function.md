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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9dee1404a8da63208bba7b7529b16eabbee3254
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745760"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="4456a-102">Функция FunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4456a-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="4456a-103">Уведомляет профилировщик о заданному идентификатору функции может быть альтернативный идентификатор для использования в [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="4456a-104">`FunctionIDMapper` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4456a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4456a-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4456a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4456a-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="4456a-107">[in] Идентификатор функции для повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4456a-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="4456a-108">[out] Указатель на значение, заданное профилировщиком `true` Если требуется получать `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` обратных вызовов; в противном случае это значение устанавливается равным `false`.</span><span class="sxs-lookup"><span data-stu-id="4456a-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4456a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4456a-109">Return Value</span></span>  
 <span data-ttu-id="4456a-110">Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="4456a-111">Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4456a-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="4456a-112">В противном случае возвращаемое значение null будет приводят к непредсказуемым результатам, включая возможное прерывание процесса.</span><span class="sxs-lookup"><span data-stu-id="4456a-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4456a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4456a-113">Remarks</span></span>  
 <span data-ttu-id="4456a-114">`FunctionIDMapper` Функция является обратным вызовом.</span><span class="sxs-lookup"><span data-stu-id="4456a-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="4456a-115">Она реализуется профилировщиком для повторного сопоставления идентификатора функции другой идентификатор, который лучше подходит для профилировщика.</span><span class="sxs-lookup"><span data-stu-id="4456a-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="4456a-116">`FunctionIDMapper` Возвращает альтернативный идентификатор, который будет использоваться для любой заданной функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="4456a-117">Затем ядро выполнения выполняет запрос профилировщика, передав этот альтернативный идентификатор в дополнение к традиционному Идентификатору функции профилировщика в `clientData` параметр `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` ловушки, для идентификации функция, для которого вызывается обработчик.</span><span class="sxs-lookup"><span data-stu-id="4456a-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="4456a-118">Можно использовать [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) метод, чтобы задать реализацию `FunctionIDMapper` функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="4456a-119">Можно вызвать `ICorProfilerInfo::SetFunctionIDMapper` метод только один раз и мы рекомендуем, поэтому в выполнить [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4456a-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="4456a-120">По умолчанию предполагается, что профилировщик, задает COR_PRF_MONITOR_ENTERLEAVE флаг с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), и который устанавливает обработчики через [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) или [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должны получать `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` обратных вызовов для каждой функции.</span><span class="sxs-lookup"><span data-stu-id="4456a-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="4456a-121">Тем не менее, профилировщики могут реализовать `FunctionIDMapper` для выборочно избежать получения этих обратных вызовов для определенных функций, задав `pbHookFunction` для `false`.</span><span class="sxs-lookup"><span data-stu-id="4456a-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="4456a-122">Средства профилирования должны быть устойчивы к ситуации, где несколько потоков профилируемого приложения вызывают метод или функция с тем же одновременно.</span><span class="sxs-lookup"><span data-stu-id="4456a-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="4456a-123">В таких случаях профилировщика может появиться несколько `FunctionIDMapper` обратные вызовы для того же `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="4456a-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="4456a-124">Профилировщик должен не забудьте вернуть те значения из этого обратного вызова, когда он вызывается несколько раз с тем же `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="4456a-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4456a-125">Требования</span><span class="sxs-lookup"><span data-stu-id="4456a-125">Requirements</span></span>  
 <span data-ttu-id="4456a-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4456a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4456a-127">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="4456a-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4456a-128">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4456a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4456a-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4456a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4456a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4456a-130">See also</span></span>

- [<span data-ttu-id="4456a-131">Метод SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="4456a-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="4456a-132">Функция FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="4456a-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [<span data-ttu-id="4456a-133">Функция FunctionEnter2</span><span class="sxs-lookup"><span data-stu-id="4456a-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="4456a-134">Функция FunctionLeave2</span><span class="sxs-lookup"><span data-stu-id="4456a-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="4456a-135">Функция FunctionTailcall2</span><span class="sxs-lookup"><span data-stu-id="4456a-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="4456a-136">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="4456a-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
