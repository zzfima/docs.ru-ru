---
title: Метод ICorProfilerCallback::Initialize
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16001c4af2bcd8aa8d5fff6b06fa8c275bc24cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191007"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="eab6a-102">Метод ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="eab6a-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="eab6a-103">Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="eab6a-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eab6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eab6a-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eab6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eab6a-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="eab6a-106">[в](/cpp/atl/iunknown) интерфейс, профилировщик должен запросить для [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="eab6a-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eab6a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="eab6a-107">Remarks</span></span>  
 <span data-ttu-id="eab6a-108">`Initialize` Вызов является единственной возможностью, чтобы включить (или отключить) обратные вызовы, которые являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="eab6a-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="eab6a-109">После включения обратный вызов по `Initialize` вызвать, его нельзя отключить позже с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="eab6a-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="eab6a-110">Значение COR_PRF_MONITOR_IMMUTABLE [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления указывает, какие события являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="eab6a-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eab6a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="eab6a-111">Requirements</span></span>  
 <span data-ttu-id="eab6a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eab6a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eab6a-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eab6a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eab6a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eab6a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="eab6a-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="eab6a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eab6a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="eab6a-116">See also</span></span>

- [<span data-ttu-id="eab6a-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="eab6a-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="eab6a-118">Метод Shutdown</span><span class="sxs-lookup"><span data-stu-id="eab6a-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
