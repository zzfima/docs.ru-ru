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
ms.openlocfilehash: e6c21e5ec9491e2ccade48a5019b284e333b5ead
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865939"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="dd298-102">Метод ICorProfilerCallback::RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="dd298-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="dd298-103">Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd298-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd298-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd298-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="dd298-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="dd298-105">Remarks</span></span>  
 <span data-ttu-id="dd298-106">Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd298-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="dd298-107">На этом этапе они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="dd298-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="dd298-108">Это также относится к новым потокам, которые вводят среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd298-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="dd298-109">Все потоки в среде выполнения либо приостанавливаются немедленно, если они уже находятся в коде для преобразования, либо если они запросят приостановить работу в случае, если они достигают кода источника.</span><span class="sxs-lookup"><span data-stu-id="dd298-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="dd298-110">Обратный вызов `RuntimeSuspendFinished` будет гарантированно выполняться в том же потоке, что и обратный вызов [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dd298-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd298-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dd298-111">Requirements</span></span>  
 <span data-ttu-id="dd298-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd298-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd298-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dd298-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dd298-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd298-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd298-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd298-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd298-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd298-116">See also</span></span>

- [<span data-ttu-id="dd298-117">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dd298-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="dd298-118">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="dd298-118">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
