---
title: Метод ICorProfilerCallback::RuntimeSuspendFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07e2ebe8afe6002dee6c45f56fa1f11a4083d6bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145604"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="c2ee0-102">Метод ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="c2ee0-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="c2ee0-103">Уведомляет профилировщика о том, что среда выполнения завершила приостановку всех потоков среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2ee0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2ee0-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2ee0-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2ee0-105">Remarks</span></span>  
 <span data-ttu-id="c2ee0-106">Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжать выполняться, пока они пытаются повторно ввести среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="c2ee0-107">В этот момент они также будут приостановлены до среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="c2ee0-108">Это также относится к новых потоков, выполняющих вход в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="c2ee0-109">Все потоки в среде выполнения, либо приостановлен немедленно, если они уже такого кода или получают запрос на приостановку по достижении такого кода.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="c2ee0-110">`RuntimeSuspendFinished` Обратный вызов гарантированно происходит в том же потоке, что [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c2ee0-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2ee0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c2ee0-111">Requirements</span></span>  
 <span data-ttu-id="c2ee0-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2ee0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2ee0-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2ee0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2ee0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2ee0-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c2ee0-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c2ee0-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2ee0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c2ee0-116">See also</span></span>

- [<span data-ttu-id="c2ee0-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c2ee0-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c2ee0-118">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="c2ee0-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
