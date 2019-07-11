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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20fd186c32857fe547c47d06874f635a5628b178
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750766"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="c23b1-102">Метод ICorProfilerCallback::RuntimeSuspendStarted</span><span class="sxs-lookup"><span data-stu-id="c23b1-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="c23b1-103">Уведомляет профилировщик о том, что среда выполнения будет приостанавливать все потоки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c23b1-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c23b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c23b1-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c23b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c23b1-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="c23b1-106">[in] Значение [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) перечисление, указывающее причину приостановки.</span><span class="sxs-lookup"><span data-stu-id="c23b1-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c23b1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c23b1-107">Remarks</span></span>  
 <span data-ttu-id="c23b1-108">Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжать выполняться, пока они пытаются повторно ввести среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c23b1-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="c23b1-109">В этот момент они также будут приостановлены до среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="c23b1-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="c23b1-110">Это также относится к новых потоков, выполняющих вход в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="c23b1-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="c23b1-111">Все потоки в среде выполнения, либо приостановлен немедленно, если они уже такого кода или получают запрос на приостановку по достижении такого кода.</span><span class="sxs-lookup"><span data-stu-id="c23b1-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c23b1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c23b1-112">Requirements</span></span>  
 <span data-ttu-id="c23b1-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c23b1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c23b1-114">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c23b1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c23b1-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c23b1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c23b1-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c23b1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23b1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c23b1-117">See also</span></span>

- [<span data-ttu-id="c23b1-118">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c23b1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c23b1-119">Метод RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="c23b1-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="c23b1-120">Метод RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="c23b1-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
