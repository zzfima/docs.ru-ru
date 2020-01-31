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
ms.openlocfilehash: c8645bf828d0ad99bd25c1909cbee3314a11abf9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865874"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="b4ce0-102">Метод ICorProfilerCallback::RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="b4ce0-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="b4ce0-103">Уведомляет профилировщик о том, что указанный поток был приостановлен или готов к приостановке.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ce0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4ce0-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ce0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4ce0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b4ce0-106">окне Идентификатор приостановленного потока.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4ce0-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b4ce0-107">Remarks</span></span>  
 <span data-ttu-id="b4ce0-108">`RuntimeThreadSuspended`ное уведомление может возникнуть в любое время между методами [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) и связанными обратными вызовами [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b4ce0-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="b4ce0-109">Уведомления, происходящие между параметрами [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и `RuntimeResumeStarted`, относятся к потокам, которые были запущены в неуправляемом коде и были приостановлены при входе в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="b4ce0-110">Как правило, этот обратный вызов происходит сразу после приостановки потока.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="b4ce0-111">Однако если текущий выполняющийся поток (поток, вызвавший этот обратный вызов) является приостановленным, этот обратный вызов произойдет непосредственно перед приостановкой потока.</span><span class="sxs-lookup"><span data-stu-id="b4ce0-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ce0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b4ce0-112">Requirements</span></span>  
 <span data-ttu-id="b4ce0-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ce0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ce0-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4ce0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4ce0-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4ce0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4ce0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ce0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ce0-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4ce0-117">See also</span></span>

- [<span data-ttu-id="b4ce0-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b4ce0-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b4ce0-119">Метод RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="b4ce0-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
