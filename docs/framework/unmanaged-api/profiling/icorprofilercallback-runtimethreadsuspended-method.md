---
title: Метод ICorProfilerCallback::RuntimeThreadSuspended
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0748802599926f4ec218362e6f7d086aab2d8f9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080232"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="f8085-102">Метод ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="f8085-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="f8085-103">Уведомляет профилировщик, что указанный поток был приостановлен или будет приостановлено.</span><span class="sxs-lookup"><span data-stu-id="f8085-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8085-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8085-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8085-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8085-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f8085-106">[in] Идентификатор потока, который был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="f8085-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8085-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8085-107">Remarks</span></span>  
 <span data-ttu-id="f8085-108">`RuntimeThreadSuspended` Уведомлений может произойти любое время между [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) и связанным [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="f8085-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="f8085-109">Уведомления, которые выполняются между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` для потоков, которые были запущены в неуправляемом коде и были приостановлены после входа в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8085-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="f8085-110">Как правило этот обратный вызов происходит только в том случае, после приостановки потока.</span><span class="sxs-lookup"><span data-stu-id="f8085-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="f8085-111">Тем не менее если текущий выполняемый поток (поток, вызвавший этот обратный вызов) является тот, который приостанавливается, этот обратный вызов возникает непосредственно перед поток приостановлен.</span><span class="sxs-lookup"><span data-stu-id="f8085-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8085-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f8085-112">Requirements</span></span>  
 <span data-ttu-id="f8085-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8085-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8085-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8085-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8085-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8085-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f8085-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f8085-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8085-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f8085-117">See also</span></span>

- [<span data-ttu-id="f8085-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f8085-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f8085-119">Метод RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="f8085-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
