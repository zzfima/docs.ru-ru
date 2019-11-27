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
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446972"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="67a2b-102">Метод ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="67a2b-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="67a2b-103">Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="67a2b-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67a2b-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="67a2b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="67a2b-105">Remarks</span></span>  
 <span data-ttu-id="67a2b-106">Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="67a2b-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="67a2b-107">На этом этапе они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="67a2b-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="67a2b-108">Это также относится к новым потокам, которые вводят среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="67a2b-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="67a2b-109">Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже находятся в коде для преобразования, либо если они запросят приостановить работу в случае, если они достигают кода источника.</span><span class="sxs-lookup"><span data-stu-id="67a2b-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="67a2b-110">Обратный вызов `RuntimeSuspendFinished` будет гарантированно выполняться в том же потоке, что и обратный вызов [ICorProfilerCallback:: рунтимесуспендстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="67a2b-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a2b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="67a2b-111">Requirements</span></span>  
 <span data-ttu-id="67a2b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a2b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a2b-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67a2b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67a2b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67a2b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67a2b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a2b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a2b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="67a2b-116">See also</span></span>

- [<span data-ttu-id="67a2b-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="67a2b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="67a2b-118">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="67a2b-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
