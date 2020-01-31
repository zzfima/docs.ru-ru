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
ms.openlocfilehash: 285bdd3f2a96d3c6cb0039382d9944e48c49971a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865913"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="a8497-102">Метод ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="a8497-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="a8497-103">Уведомляет профилировщик о том, что среда выполнения прервал приостановленную приостановку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a8497-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8497-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8497-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a8497-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="a8497-105">Remarks</span></span>  
 <span data-ttu-id="a8497-106">Приостановка во время выполнения может быть прервана, если два потока одновременно пытаются приостановить выполнение.</span><span class="sxs-lookup"><span data-stu-id="a8497-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="a8497-107">Обратный вызов [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) или обратный вызов `RuntimeSuspendAborted` выполняется в одном потоке после обратного вызова [ICorProfilerCallback:: рунтимесуспендстартед](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a8497-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="a8497-108">Функция обратного вызова `RuntimeSuspendAborted` будет гарантированно выполняться в том же потоке, что и обратный вызов `RuntimeSuspendStarted`.</span><span class="sxs-lookup"><span data-stu-id="a8497-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8497-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a8497-109">Requirements</span></span>  
 <span data-ttu-id="a8497-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8497-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8497-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8497-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8497-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8497-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8497-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8497-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8497-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8497-114">See also</span></span>

- [<span data-ttu-id="a8497-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a8497-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
