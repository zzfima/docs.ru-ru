---
title: "Метод ICorProfilerCallback::RuntimeSuspendAborted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendAborted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2d1c181a471763ea0220c081d64af915ca6be149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="ef3a2-102">Метод ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="ef3a2-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="ef3a2-103">Уведомляет профилировщик о том, что среда выполнения прервала приостановку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef3a2-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef3a2-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ef3a2-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef3a2-105">Remarks</span></span>  
 <span data-ttu-id="ef3a2-106">Приостановка во время выполнения может быть прервана, если два потока одновременно пытаются приостановить среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef3a2-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="ef3a2-107">Либо [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) обратного вызова или `RuntimeSuspendAborted` обратный вызов будет выполняться в следующих однопоточное [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="ef3a2-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="ef3a2-108">`RuntimeSuspendAborted` Обратный вызов гарантированно происходит в том же потоке, как `RuntimeSuspendStarted` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ef3a2-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3a2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ef3a2-109">Requirements</span></span>  
 <span data-ttu-id="ef3a2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef3a2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3a2-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef3a2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef3a2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef3a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef3a2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3a2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ef3a2-114">See Also</span></span>  
 [<span data-ttu-id="ef3a2-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ef3a2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
