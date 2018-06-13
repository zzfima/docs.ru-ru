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
ms.openlocfilehash: c5726c0a563c8937f6f4fff184b7b924d501fa83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451910"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="7a496-102">Метод ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="7a496-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="7a496-103">Уведомляет профилировщик о том, что среда выполнения прервала приостановку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="7a496-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a496-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a496-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7a496-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a496-105">Remarks</span></span>  
 <span data-ttu-id="7a496-106">Приостановка во время выполнения может быть прервана, если два потока одновременно пытаются приостановить среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="7a496-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="7a496-107">Либо [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) обратного вызова или `RuntimeSuspendAborted` обратный вызов будет выполняться в следующих однопоточное [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="7a496-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="7a496-108">`RuntimeSuspendAborted` Обратный вызов гарантированно происходит в том же потоке, как `RuntimeSuspendStarted` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="7a496-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a496-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7a496-109">Requirements</span></span>  
 <span data-ttu-id="7a496-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a496-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a496-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a496-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a496-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a496-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a496-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a496-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a496-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7a496-114">See Also</span></span>  
 [<span data-ttu-id="7a496-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7a496-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
