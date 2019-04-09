---
title: Интерфейс ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107553"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="f5e62-102">Интерфейс ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="f5e62-102">ICorDebugController Interface</span></span>

<span data-ttu-id="f5e62-103">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="f5e62-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5e62-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f5e62-104">Methods</span></span>  
  
|<span data-ttu-id="f5e62-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f5e62-105">Method</span></span>|<span data-ttu-id="f5e62-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f5e62-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="f5e62-107">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="f5e62-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="f5e62-108">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="f5e62-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="f5e62-109">Метод Continue</span><span class="sxs-lookup"><span data-stu-id="f5e62-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="f5e62-110">Возобновляет выполнение управляемых потоков после вызова [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5e62-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="f5e62-111">Метод Detach</span><span class="sxs-lookup"><span data-stu-id="f5e62-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="f5e62-112">Отключает отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="f5e62-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="f5e62-113">Метод EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="f5e62-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="f5e62-114">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="f5e62-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="f5e62-115">Метод HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="f5e62-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="f5e62-116">Получает значение, указывающее ли любой управляемый оно для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="f5e62-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="f5e62-117">Метод IsRunning</span><span class="sxs-lookup"><span data-stu-id="f5e62-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="f5e62-118">Получает значение, указывающее, потоки в процессе, в настоящее время работают ли свободно.</span><span class="sxs-lookup"><span data-stu-id="f5e62-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="f5e62-119">Метод SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="f5e62-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="f5e62-120">Задает состояние отладки все управляемые потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="f5e62-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="f5e62-121">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="f5e62-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="f5e62-122">Выполняет совместную остановку во всех потоках, работающих под управлением управляемого кода в процессе.</span><span class="sxs-lookup"><span data-stu-id="f5e62-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="f5e62-123">Метод Terminate</span><span class="sxs-lookup"><span data-stu-id="f5e62-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="f5e62-124">Завершает процесс с помощью указанного кода выхода.</span><span class="sxs-lookup"><span data-stu-id="f5e62-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5e62-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5e62-125">Remarks</span></span>  
 <span data-ttu-id="f5e62-126">Если `ICorDebugController` является управление процессом, в том числе все потоки процесса.</span><span class="sxs-lookup"><span data-stu-id="f5e62-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="f5e62-127">Если `ICorDebugController` является управление домен приложения, в область входит только потоки конкретного домена приложений.</span><span class="sxs-lookup"><span data-stu-id="f5e62-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5e62-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f5e62-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e62-129">Требования</span><span class="sxs-lookup"><span data-stu-id="f5e62-129">Requirements</span></span>  
 <span data-ttu-id="f5e62-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e62-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e62-131">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5e62-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5e62-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5e62-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f5e62-133">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f5e62-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5e62-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f5e62-134">See also</span></span>

- [<span data-ttu-id="f5e62-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f5e62-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
