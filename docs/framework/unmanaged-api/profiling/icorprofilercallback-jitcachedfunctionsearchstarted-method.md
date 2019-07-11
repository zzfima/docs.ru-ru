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
ms.openlocfilehash: f4d35179b8ae35c03370cc3798609d6ed430cde3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782852"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="f7b56-102">Метод ICorProfilerCallback::JITCachedFunctionSearchStarted</span><span class="sxs-lookup"><span data-stu-id="f7b56-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="f7b56-103">Уведомляет профилировщик о начале поиска для функции, который был скомпилирован с помощью генератором машинных образов (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="f7b56-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7b56-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7b56-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7b56-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f7b56-106">[in] Идентификатор функции, для которой выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="f7b56-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="f7b56-107">[out] `true` Если ядро выполнения следует использовать кэшированную версию функции, (при наличии); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f7b56-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="f7b56-108">Если значение равно `false`, ядро выполнения JIT-компиляцию функции, вместо того чтобы использовать версию, которая не является JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f7b56-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7b56-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7b56-109">Remarks</span></span>  
 <span data-ttu-id="f7b56-110">В .NET Framework версии 2.0 `JITCachedFunctionSearchStarted` и [метод ICorProfilerCallback::JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) обратные вызовы не будут совершаться для всех функций в обычных образов NGen.</span><span class="sxs-lookup"><span data-stu-id="f7b56-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="f7b56-111">Только образы NGen, оптимизированные для профиля будут создавать обратные вызовы для всех функций в образе.</span><span class="sxs-lookup"><span data-stu-id="f7b56-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="f7b56-112">Тем не менее из-за дополнительных издержек, профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если планируется использовать эти обратные вызовы для принудительного функции скомпилированного just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="f7b56-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="f7b56-113">В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.</span><span class="sxs-lookup"><span data-stu-id="f7b56-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="f7b56-114">Профилировщики должны поддерживать ситуации, где несколько потоков профилируемого приложения вызывают тот же метод одновременно.</span><span class="sxs-lookup"><span data-stu-id="f7b56-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="f7b56-115">Например, поток A вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, задав *pbUseCachedFunction*значение false, чтобы принудительно JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="f7b56-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="f7b56-116">Поток, затем вызывает [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="f7b56-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="f7b56-117">Теперь поток B вызывает `JITCachedFunctionSearchStarted` для той же функции.</span><span class="sxs-lookup"><span data-stu-id="f7b56-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="f7b56-118">Несмотря на то, что профилировщик заявила о своем намерении выполнить JIT-компиляцию функции, профилировщик получает обратный вызов, так как поток B отправляет обратный вызов, прежде чем профилировщик ответил на вызов потока A `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="f7b56-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="f7b56-119">Порядок, в котором потоки выполняют вызовы зависит от того, как запланировано потоков.</span><span class="sxs-lookup"><span data-stu-id="f7b56-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="f7b56-120">Когда профилировщик получает обратных вызовов, его необходимо задать значение ссылается `pbUseCachedFunction` то же значение для всех обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="f7b56-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="f7b56-121">То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с тем же `functionId` значение, профилировщик должен вернуть же каждый раз.</span><span class="sxs-lookup"><span data-stu-id="f7b56-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b56-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f7b56-122">Requirements</span></span>  
 <span data-ttu-id="f7b56-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b56-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b56-124">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7b56-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7b56-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7b56-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7b56-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b56-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b56-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f7b56-127">See also</span></span>

- [<span data-ttu-id="f7b56-128">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f7b56-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
