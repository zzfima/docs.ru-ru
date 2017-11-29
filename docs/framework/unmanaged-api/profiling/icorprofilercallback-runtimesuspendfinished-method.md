---
title: "Метод ICorProfilerCallback::RuntimeSuspendFinished"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c922ee4f986df22f213820b8aed60ea28a76377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="dab4b-102">Метод ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="dab4b-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="dab4b-103">Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dab4b-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dab4b-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dab4b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="dab4b-105">Remarks</span></span>  
 <span data-ttu-id="dab4b-106">Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжить выполнение, пока они пытаются заново ввести среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dab4b-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="dab4b-107">В этот момент они также будут приостановлены до возобновления работы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dab4b-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="dab4b-108">Это справедливо и для новых потоков, выполняющих вход в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="dab4b-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="dab4b-109">Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже такого кода или получают запрос на приостановку по достижении такого кода.</span><span class="sxs-lookup"><span data-stu-id="dab4b-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="dab4b-110">`RuntimeSuspendFinished` Обратный вызов гарантированно происходит в том же потоке, как [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="dab4b-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dab4b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dab4b-111">Requirements</span></span>  
 <span data-ttu-id="dab4b-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab4b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab4b-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dab4b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dab4b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dab4b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dab4b-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab4b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab4b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dab4b-116">See Also</span></span>  
 [<span data-ttu-id="dab4b-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dab4b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="dab4b-118">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="dab4b-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
