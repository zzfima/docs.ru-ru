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
ms.openlocfilehash: 7673d6fac2626bc0059204ea77a23686b11638cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452739"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="fda48-102">Метод ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="fda48-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="fda48-103">Уведомляет профилировщик, что указанный поток приостановлен или которой нужно приостановить.</span><span class="sxs-lookup"><span data-stu-id="fda48-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fda48-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fda48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fda48-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fda48-106">[in] Идентификатор потока, который был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="fda48-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fda48-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fda48-107">Remarks</span></span>  
 <span data-ttu-id="fda48-108">`RuntimeThreadSuspended` Уведомление может произойти в любое время между [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) и связанное с ним [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="fda48-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="fda48-109">Уведомления, которые происходят между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted` для потоков, которые были запущены в неуправляемом коде и были приостановлены после входа в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="fda48-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="fda48-110">Как правило этот обратный вызов происходит после приостановления потока.</span><span class="sxs-lookup"><span data-stu-id="fda48-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="fda48-111">Тем не менее если текущий выполняемый поток (поток, вызвавший этот обратный вызов), приостановке, этот обратный вызов будет выполняться перед приостанавливается поток.</span><span class="sxs-lookup"><span data-stu-id="fda48-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fda48-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fda48-112">Requirements</span></span>  
 <span data-ttu-id="fda48-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fda48-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fda48-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fda48-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fda48-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fda48-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fda48-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fda48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda48-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fda48-117">See Also</span></span>  
 [<span data-ttu-id="fda48-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fda48-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="fda48-119">Метод RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="fda48-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
