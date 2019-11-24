---
title: Метод ICorProfilerCallback::RuntimeSuspendStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: 1777fa1f2537b6d28d771661ca463564d74d8550
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433507"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="7817a-102">Метод ICorProfilerCallback::RuntimeSuspendStarted</span><span class="sxs-lookup"><span data-stu-id="7817a-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="7817a-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span><span class="sxs-lookup"><span data-stu-id="7817a-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7817a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7817a-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7817a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7817a-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="7817a-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span><span class="sxs-lookup"><span data-stu-id="7817a-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7817a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="7817a-107">Remarks</span></span>  
 <span data-ttu-id="7817a-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span><span class="sxs-lookup"><span data-stu-id="7817a-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="7817a-109">At that point they will also be suspended until the runtime resumes.</span><span class="sxs-lookup"><span data-stu-id="7817a-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="7817a-110">This also applies to new threads that enter the runtime.</span><span class="sxs-lookup"><span data-stu-id="7817a-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="7817a-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span><span class="sxs-lookup"><span data-stu-id="7817a-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7817a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7817a-112">Requirements</span></span>  
 <span data-ttu-id="7817a-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7817a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7817a-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7817a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7817a-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7817a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7817a-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7817a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7817a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7817a-117">See also</span></span>

- [<span data-ttu-id="7817a-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7817a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7817a-119">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="7817a-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="7817a-120">Метод RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="7817a-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
