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
ms.openlocfilehash: 964ea11b8e8c8f494066249f7da2057970d7e8f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866264"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="12667-102">Метод ICorProfilerCallback::JITCachedFunctionSearchStarted</span><span class="sxs-lookup"><span data-stu-id="12667-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="12667-103">Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью генератора образов в машинном кодах (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="12667-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12667-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12667-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12667-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12667-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="12667-106">\[в] идентификатор функции, для которой выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="12667-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="12667-107">\[out] `true`, если подсистема выполнения должна использовать кэшированную версию функции (если она доступна); в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="12667-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="12667-108">Если значение равно `false`, подсистема выполнения JIT-компилирует функцию вместо использования версии, которая не является JIT-скомпилированной.</span><span class="sxs-lookup"><span data-stu-id="12667-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="12667-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="12667-109">Remarks</span></span>  
 <span data-ttu-id="12667-110">В .NET Framework версии 2,0 обратные вызовы методов `JITCachedFunctionSearchStarted` и [ICorProfilerCallback:: житкачедфунктионсеарчфинишед](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) не будут выполняться для всех функций в обычных образах Ngen.</span><span class="sxs-lookup"><span data-stu-id="12667-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="12667-111">Только образы NGen, оптимизированные для профиля, будут создавать обратные вызовы для всех функций в образе.</span><span class="sxs-lookup"><span data-stu-id="12667-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="12667-112">Однако из-за дополнительных издержек профилировщик должен запросить оптимизированные профилировщиком генераторы NGen только в том случае, если планируется использовать эти обратные вызовы для принудительной компиляции функции JIT (JIT).</span><span class="sxs-lookup"><span data-stu-id="12667-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="12667-113">В противном случае профилировщик должен использовать отложенную стратегию для сбора сведений о функции.</span><span class="sxs-lookup"><span data-stu-id="12667-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="12667-114">Профилировщики должны поддерживать случаи, когда несколько потоков профилированного приложения одновременно вызывают один и тот же метод.</span><span class="sxs-lookup"><span data-stu-id="12667-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="12667-115">Например, поток а вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, устанавливая для *пбусекачедфунктион*значение false для ПРИНУДИТЕЛЬной JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="12667-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="12667-116">Затем поток а вызывает метод [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="12667-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="12667-117">Теперь поток B вызывает `JITCachedFunctionSearchStarted` для одной и той же функции.</span><span class="sxs-lookup"><span data-stu-id="12667-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="12667-118">Несмотря на то, что профилировщик заявляет намерение выполнить JIT-компиляцию функции, профилировщик получает второй обратный вызов, так как поток B отправляет обратный вызов до того, как профилировщик ответит на вызов потока A в `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="12667-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="12667-119">Порядок, в котором потоки выполняют вызовы, зависит от того, как запланированы потоки.</span><span class="sxs-lookup"><span data-stu-id="12667-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="12667-120">Когда профилировщик получает дублирующиеся обратные вызовы, он должен задать значение, на которое ссылается `pbUseCachedFunction`, на то же значение для всех повторяющихся обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="12667-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="12667-121">То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с одним и тем же `functionId` значением, профилировщик должен каждый раз отвечать на эти же значения.</span><span class="sxs-lookup"><span data-stu-id="12667-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12667-122">Требования</span><span class="sxs-lookup"><span data-stu-id="12667-122">Requirements</span></span>  
 <span data-ttu-id="12667-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12667-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12667-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12667-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12667-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12667-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12667-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12667-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12667-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="12667-127">See also</span></span>

- [<span data-ttu-id="12667-128">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="12667-128">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
