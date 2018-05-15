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
ms.openlocfilehash: cd53d74dfe8199617df47e46641b71203abf6e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="7bef5-102">Метод ICorProfilerCallback::Initialize</span><span class="sxs-lookup"><span data-stu-id="7bef5-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="7bef5-103">Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR (CLR).</span><span class="sxs-lookup"><span data-stu-id="7bef5-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bef5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bef5-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bef5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bef5-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="7bef5-106">[в](/cpp/atl/iunknown) интерфейс, профилировщик должен запрашивать [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) указатель на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7bef5-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bef5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7bef5-107">Remarks</span></span>  
 <span data-ttu-id="7bef5-108">`Initialize` Вызов является единственная возможность включить (или отключить) обратные вызовы, которые являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="7bef5-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="7bef5-109">После включения обратный вызов по `Initialize` вызвать, его нельзя отключить позже с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="7bef5-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="7bef5-110">Значение COR_PRF_MONITOR_IMMUTABLE [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления указывает, какие события являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="7bef5-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bef5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7bef5-111">Requirements</span></span>  
 <span data-ttu-id="7bef5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bef5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bef5-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7bef5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7bef5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bef5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bef5-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bef5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bef5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7bef5-116">See Also</span></span>  
 [<span data-ttu-id="7bef5-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7bef5-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7bef5-118">Метод Shutdown</span><span class="sxs-lookup"><span data-stu-id="7bef5-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
