---
title: "Метод ICorProfilerCallback::RuntimeThreadSuspended"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadSuspended
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4d2ab0244e898a60db8fe392ccbd8c0ebfd5523
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="1782f-102">Метод ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="1782f-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="1782f-103">Уведомляет профилировщик, что указанный поток приостановлен или которой нужно приостановить.</span><span class="sxs-lookup"><span data-stu-id="1782f-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1782f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1782f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1782f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1782f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1782f-106">[in] Идентификатор потока, который был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="1782f-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1782f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1782f-107">Remarks</span></span>  
 <span data-ttu-id="1782f-108">`RuntimeThreadSuspended` Уведомление может произойти в любое время между [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) и связанное с ним [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="1782f-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="1782f-109">Уведомления, которые происходят между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` для потоков, которые были запущены в неуправляемом коде и были приостановлены после входа в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="1782f-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="1782f-110">Как правило этот обратный вызов происходит после приостановления потока.</span><span class="sxs-lookup"><span data-stu-id="1782f-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="1782f-111">Тем не менее если текущий выполняемый поток (поток, вызвавший этот обратный вызов), приостановке, этот обратный вызов будет выполняться перед приостанавливается поток.</span><span class="sxs-lookup"><span data-stu-id="1782f-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1782f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1782f-112">Requirements</span></span>  
 <span data-ttu-id="1782f-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1782f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1782f-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1782f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1782f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1782f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1782f-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1782f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1782f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1782f-117">See Also</span></span>  
 [<span data-ttu-id="1782f-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="1782f-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1782f-119">Метод RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="1782f-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
