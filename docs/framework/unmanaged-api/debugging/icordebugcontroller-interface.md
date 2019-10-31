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
ms.openlocfilehash: 27f991c12ea7786d6146b5731848ca5ad3a37e21
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125375"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="39482-102">Интерфейс ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="39482-102">ICorDebugController Interface</span></span>

<span data-ttu-id="39482-103">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="39482-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39482-104">Методы</span><span class="sxs-lookup"><span data-stu-id="39482-104">Methods</span></span>  
  
|<span data-ttu-id="39482-105">Метод</span><span class="sxs-lookup"><span data-stu-id="39482-105">Method</span></span>|<span data-ttu-id="39482-106">Описание</span><span class="sxs-lookup"><span data-stu-id="39482-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="39482-107">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="39482-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="39482-108">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="39482-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="39482-109">Метод Continue</span><span class="sxs-lookup"><span data-stu-id="39482-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="39482-110">Возобновляет выполнение управляемых потоков после вызова [ICorDebugController:: останавливаться](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="39482-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="39482-111">Метод Detach</span><span class="sxs-lookup"><span data-stu-id="39482-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="39482-112">Отсоединяет отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="39482-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="39482-113">Метод EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="39482-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="39482-114">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="39482-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="39482-115">Метод HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="39482-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="39482-116">Возвращает значение, указывающее, находятся ли в очереди управляемые обратные вызовы для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="39482-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="39482-117">Метод IsRunning</span><span class="sxs-lookup"><span data-stu-id="39482-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="39482-118">Возвращает значение, указывающее, выполняются ли в настоящий момент потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="39482-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="39482-119">Метод SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="39482-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="39482-120">Задает состояние отладки всех управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="39482-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="39482-121">Метод Stop</span><span class="sxs-lookup"><span data-stu-id="39482-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="39482-122">Выполняет совместную работу во всех потоках, где выполняется управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="39482-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="39482-123">Метод Terminate</span><span class="sxs-lookup"><span data-stu-id="39482-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="39482-124">Завершает процесс с указанным кодом выхода.</span><span class="sxs-lookup"><span data-stu-id="39482-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39482-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="39482-125">Remarks</span></span>  
 <span data-ttu-id="39482-126">Если `ICorDebugController` управляет процессом, область включает все потоки процесса.</span><span class="sxs-lookup"><span data-stu-id="39482-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="39482-127">Если `ICorDebugController` управляет доменом приложения, область включает только потоки этого конкретного домена приложения.</span><span class="sxs-lookup"><span data-stu-id="39482-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39482-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="39482-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39482-129">Требования</span><span class="sxs-lookup"><span data-stu-id="39482-129">Requirements</span></span>  
 <span data-ttu-id="39482-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39482-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39482-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39482-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39482-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39482-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39482-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39482-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39482-134">См. также</span><span class="sxs-lookup"><span data-stu-id="39482-134">See also</span></span>

- [<span data-ttu-id="39482-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="39482-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
