---
title: Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d97b40412b6999000a601b72904a03edf2acd08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="cb73e-102">Метод ICorProfilerCallback::JITCachedFunctionSearchStarted</span><span class="sxs-lookup"><span data-stu-id="cb73e-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="cb73e-103">Уведомляет профилировщик о начале поиска для функции, скомпилированной ранее с помощью генератором образов в машинном коде (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="cb73e-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb73e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb73e-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb73e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb73e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="cb73e-106">[in] Идентификатор функции, для которой выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="cb73e-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="cb73e-107">[out] `true` Если ядро выполнения должен использовать кэшированная версия функции (если доступно); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="cb73e-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="cb73e-108">Если значение равно `false`, ядро выполнения JIT-компиляцию функции, вместо того чтобы использовать версию, которая не является JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="cb73e-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb73e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb73e-109">Remarks</span></span>  
 <span data-ttu-id="cb73e-110">В .NET Framework версии 2.0 `JITCachedFunctionSearchStarted` и [метод ICorProfilerCallback::JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) обратные вызовы не будут совершаться для всех функций в обычных образов NGen.</span><span class="sxs-lookup"><span data-stu-id="cb73e-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="cb73e-111">Образы NGen, оптимизированные под профиль создаст обратные вызовы для всех функций в образе.</span><span class="sxs-lookup"><span data-stu-id="cb73e-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="cb73e-112">Однако из-за дополнительных служебных данных профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если он будет использовать эти обратные вызовы для принудительного функцией скомпилированных just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="cb73e-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="cb73e-113">В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.</span><span class="sxs-lookup"><span data-stu-id="cb73e-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="cb73e-114">Профилировщики должны поддерживать ситуации, когда несколько потоков профилируемого приложения вызывают тот же метод одновременно.</span><span class="sxs-lookup"><span data-stu-id="cb73e-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="cb73e-115">Например, поток A вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, устанавливая *pbUseCachedFunction*значение FALSE, чтобы принудительно JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="cb73e-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="cb73e-116">Затем вызывает потоком [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb73e-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="cb73e-117">Теперь поток вызывает метод B `JITCachedFunctionSearchStarted` для той же функции.</span><span class="sxs-lookup"><span data-stu-id="cb73e-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="cb73e-118">Несмотря на то, что профилировщик объявил его намерение JIT-компиляцию функции, профилировщик получает обратный вызов, поскольку поток B отправляет обратный вызов перед профилировщик ответил на вызов потоком `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="cb73e-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="cb73e-119">Порядок, в котором потоки выполняют вызовы зависит от того, как они запланированы.</span><span class="sxs-lookup"><span data-stu-id="cb73e-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="cb73e-120">Когда профилировщик получает дублирующиеся обратные вызовы, его значение должно быть ссылается `pbUseCachedFunction` то же значение для всех обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cb73e-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="cb73e-121">То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с одинаковым `functionId` значение, профилировщик должен ответить же каждый раз.</span><span class="sxs-lookup"><span data-stu-id="cb73e-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb73e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="cb73e-122">Requirements</span></span>  
 <span data-ttu-id="cb73e-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb73e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb73e-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb73e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb73e-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb73e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb73e-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb73e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb73e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="cb73e-127">See Also</span></span>  
 [<span data-ttu-id="cb73e-128">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cb73e-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
