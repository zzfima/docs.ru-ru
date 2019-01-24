---
title: Перечисление COR_PRF_SUSPEND_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b40533553ccd7a3339a8a3ee0c8b47879efd38ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742465"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="b0740-102">Перечисление COR_PRF_SUSPEND_REASON</span><span class="sxs-lookup"><span data-stu-id="b0740-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="b0740-103">Указывает причину приостановки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0740-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0740-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0740-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="b0740-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0740-105">Members</span></span>  
  
|<span data-ttu-id="b0740-106">Член</span><span class="sxs-lookup"><span data-stu-id="b0740-106">Member</span></span>|<span data-ttu-id="b0740-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0740-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="b0740-108">Среда выполнения приостановлена по неизвестной причине.</span><span class="sxs-lookup"><span data-stu-id="b0740-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="b0740-109">Среда выполнения приостановлена для обслуживания запросов на сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="b0740-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="b0740-110">Обратные вызовы с коллекцией мусора происходят между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="b0740-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="b0740-111">В приостановленном состоянии, чтобы `AppDomain` можно завершить работу.</span><span class="sxs-lookup"><span data-stu-id="b0740-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="b0740-112">Приостановленная среда выполнения, среда выполнения будет определить, какие потоки находятся в `AppDomain` то есть завершите работу и установить их выполнения при возобновлении.</span><span class="sxs-lookup"><span data-stu-id="b0740-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="b0740-113">Существуют не `AppDomain`-конкретных обратных вызовов во время этой приостановки.</span><span class="sxs-lookup"><span data-stu-id="b0740-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="b0740-114">Среда выполнения приостановлена, таким образом, возможности пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0740-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="b0740-115">Пошаговое выполнение кода гарантируется только когда компилятор just-in-time (JIT) является активным с пошагового включена.</span><span class="sxs-lookup"><span data-stu-id="b0740-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="b0740-116">Код пошагового выполнения обратные вызовы происходят между `ICorProfilerCallback::RuntimeSuspendFinished` и `ICorProfilerCallback::RuntimeResumeStarted` обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="b0740-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="b0740-117">**Примечание.**  JIT-Компилятор среды CLR не пошаговое выполнение функций в платформе .NET Framework версии 2.0, поэтому это значение не используется в версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="b0740-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="b0740-118">Среда выполнения приостановлена, таким образом, чтобы завершить работу.</span><span class="sxs-lookup"><span data-stu-id="b0740-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="b0740-119">Его необходимо приостановить все потоки для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="b0740-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="b0740-120">Среда выполнения приостановлена в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="b0740-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="b0740-121">Среда выполнения приостановлена для подготовки для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b0740-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="b0740-122">Среда выполнения приостановлена для перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="b0740-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0740-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0740-123">Remarks</span></span>  
 <span data-ttu-id="b0740-124">Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжать выполняться, пока они попытаются повторно войти в среду выполнения, после чего они также будут приостановлены среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0740-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="b0740-125">Это также относится к новых потоков, выполняющих вход в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b0740-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="b0740-126">Все потоки в среде выполнения либо приостановлен немедленно, если они находятся в такого кода, либо запрос на приостановку по достижении такого кода.</span><span class="sxs-lookup"><span data-stu-id="b0740-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0740-127">Требования</span><span class="sxs-lookup"><span data-stu-id="b0740-127">Requirements</span></span>  
 <span data-ttu-id="b0740-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0740-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0740-129">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0740-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b0740-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0740-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0740-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0740-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0740-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b0740-132">See also</span></span>
- [<span data-ttu-id="b0740-133">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="b0740-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
