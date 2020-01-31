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
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867078"
---
# <a name="cor_prf_suspend_reason-enumeration"></a><span data-ttu-id="cfdb4-102">Перечисление COR_PRF_SUSPEND_REASON</span><span class="sxs-lookup"><span data-stu-id="cfdb4-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="cfdb4-103">Указывает причину приостановки выполнения.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfdb4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfdb4-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="cfdb4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="cfdb4-105">Members</span></span>  
  
|<span data-ttu-id="cfdb4-106">Член</span><span class="sxs-lookup"><span data-stu-id="cfdb4-106">Member</span></span>|<span data-ttu-id="cfdb4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cfdb4-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="cfdb4-108">Среда выполнения приостановлена по неизвестной причине.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="cfdb4-109">Среда выполнения приостановлена для обслуживания запроса на сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="cfdb4-110">Обратные вызовы, связанные со сборкой мусора, происходят между обратными вызовами [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cfdb4-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="cfdb4-111">Среда выполнения приостановлена, чтобы можно было завершить работу `AppDomain`.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="cfdb4-112">Пока среда выполнения приостановлена, среда выполнения определит, какие потоки находятся в `AppDomain`, который завершает работу, и задайте для них значение Abort при возобновлении.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="cfdb4-113">Во время этой приостановки не `AppDomain`обратных вызовов.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="cfdb4-114">Среда выполнения приостановлена, поэтому может произойти пошаговое выполнение кода.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="cfdb4-115">Шаг с текстом выполняется, только если JIT-компилятор активен с включенным шагом в коде.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="cfdb4-116">Обратные вызовы с пошаговым выполнением кода происходят между `ICorProfilerCallback::RuntimeSuspendFinished` и `ICorProfilerCallback::RuntimeResumeStarted` обратными вызовами.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="cfdb4-117">**Примечание.**  JIT-компилятор CLR не выполняет функции в .NET Framework версии 2,0, поэтому это значение не используется в 2,0.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="cfdb4-118">Среда выполнения приостановлена, поэтому она может завершить работу.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="cfdb4-119">Чтобы завершить операцию, необходимо приостановить все потоки.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="cfdb4-120">Среда выполнения приостанавливается для внутрипроцессного процесса отладки.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="cfdb4-121">Среда выполнения приостановлена для подготовки к сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="cfdb4-122">Среда выполнения приостанавливается для повторной компиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfdb4-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="cfdb4-123">Remarks</span></span>  
 <span data-ttu-id="cfdb4-124">Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения, после чего они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="cfdb4-125">Это также относится к новым потокам, которые вводят среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="cfdb4-126">Все потоки в среде выполнения либо приостанавливаются немедленно, если они находятся в коде для преобразования, либо запрашивается их приостановка, когда они достигают кода источника.</span><span class="sxs-lookup"><span data-stu-id="cfdb4-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfdb4-127">Требования</span><span class="sxs-lookup"><span data-stu-id="cfdb4-127">Requirements</span></span>  
 <span data-ttu-id="cfdb4-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfdb4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfdb4-129">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cfdb4-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cfdb4-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfdb4-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfdb4-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfdb4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdb4-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="cfdb4-132">See also</span></span>

- [<span data-ttu-id="cfdb4-133">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="cfdb4-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
