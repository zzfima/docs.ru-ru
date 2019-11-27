---
title: Метод ICorProfilerCallback::JITCachedFunctionSearchFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: bea857f65081432eb3f5501c75af6d13805c76d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426239"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="d5029-102">Метод ICorProfilerCallback::JITCachedFunctionSearchFinished</span><span class="sxs-lookup"><span data-stu-id="d5029-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="d5029-103">Уведомляет профилировщик о завершении поиска для функции, которая была скомпилирована ранее с помощью генератора образов в машинном кодах (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="d5029-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5029-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5029-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5029-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5029-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d5029-106">окне Идентификатор функции, для которой был выполнен поиск.</span><span class="sxs-lookup"><span data-stu-id="d5029-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="d5029-107">окне Значение перечисления [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) , указывающее результат поиска.</span><span class="sxs-lookup"><span data-stu-id="d5029-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5029-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5029-108">Remarks</span></span>  
 <span data-ttu-id="d5029-109">В .NET Framework версии 2,0 обратные вызовы [ICorProfilerCallback:: JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) и `JITCachedFunctionSearchFinished` не будут выполняться для всех функций в обычных образах Ngen.</span><span class="sxs-lookup"><span data-stu-id="d5029-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="d5029-110">Только образы NGen, оптимизированные для профилировщика, будут создавать обратные вызовы для всех функций в образе.</span><span class="sxs-lookup"><span data-stu-id="d5029-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="d5029-111">Однако из-за дополнительных издержек профилировщик должен запросить оптимизированные профилировщиком генераторы NGen только в том случае, если планируется использовать эти обратные вызовы для принудительной компиляции функции JIT (JIT).</span><span class="sxs-lookup"><span data-stu-id="d5029-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="d5029-112">В противном случае профилировщик должен использовать отложенную стратегию для сбора сведений о функции.</span><span class="sxs-lookup"><span data-stu-id="d5029-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5029-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d5029-113">Requirements</span></span>  
 <span data-ttu-id="d5029-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5029-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5029-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5029-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5029-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5029-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5029-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5029-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5029-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="d5029-118">See also</span></span>

- [<span data-ttu-id="d5029-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d5029-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
