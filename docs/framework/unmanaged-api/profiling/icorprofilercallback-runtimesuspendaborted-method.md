---
title: Метод ICorProfilerCallback::RuntimeSuspendAborted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63d03e83e1688979e4fffe5d31d1f3c393f60e44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573587"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="d8736-102">Метод ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="d8736-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="d8736-103">Уведомляет профилировщик, что среда выполнения прервала приостановку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8736-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8736-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8736-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d8736-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8736-105">Remarks</span></span>  
 <span data-ttu-id="d8736-106">Приостановка выполнения может быть прерван, если двух потоков одновременно пытаются приостановить среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8736-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="d8736-107">Либо [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) обратного вызова или `RuntimeSuspendAborted` обратный вызов будет выполняться по ниже однопоточное [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="d8736-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="d8736-108">`RuntimeSuspendAborted` Обратный вызов гарантированно происходит в том же потоке, что `RuntimeSuspendStarted` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="d8736-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8736-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d8736-109">Requirements</span></span>  
 <span data-ttu-id="d8736-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8736-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8736-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8736-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8736-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8736-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8736-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8736-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8736-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d8736-114">See also</span></span>
- [<span data-ttu-id="d8736-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d8736-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
