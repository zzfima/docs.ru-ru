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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b0e78e10f092bce1c8f7762362f02b7a403c86a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122945"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="1bcef-102">Метод ICorProfilerCallback::JITCachedFunctionSearchFinished</span><span class="sxs-lookup"><span data-stu-id="1bcef-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="1bcef-103">Уведомляет профилировщик об окончании поиска для функции, который был скомпилирован с помощью генератором машинных образов (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="1bcef-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bcef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bcef-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bcef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bcef-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="1bcef-106">[in] Идентификатор функции, для которого выполняется поиск.</span><span class="sxs-lookup"><span data-stu-id="1bcef-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="1bcef-107">[in] Значение [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) перечисления, указывающее на результат поиска.</span><span class="sxs-lookup"><span data-stu-id="1bcef-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bcef-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bcef-108">Remarks</span></span>  
 <span data-ttu-id="1bcef-109">В .NET Framework версии 2.0 [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) и `JITCachedFunctionSearchFinished` обратные вызовы не будут совершаться для всех функций в обычных образов NGen.</span><span class="sxs-lookup"><span data-stu-id="1bcef-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="1bcef-110">Образы NGen, оптимизированные под профилировщик будет создавать обратные вызовы для всех функций в образе.</span><span class="sxs-lookup"><span data-stu-id="1bcef-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="1bcef-111">Тем не менее из-за дополнительных издержек, профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если планируется использовать эти обратные вызовы для принудительного функции скомпилированного just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="1bcef-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="1bcef-112">В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.</span><span class="sxs-lookup"><span data-stu-id="1bcef-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcef-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1bcef-113">Requirements</span></span>  
 <span data-ttu-id="1bcef-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcef-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1bcef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1bcef-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bcef-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1bcef-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1bcef-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1bcef-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1bcef-118">See also</span></span>

- [<span data-ttu-id="1bcef-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1bcef-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
