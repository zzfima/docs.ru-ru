---
title: "ICorDebugController интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1484d6bcfa77b8bf5fe45b2f83d5dcbff02f907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="71618-102">ICorDebugController интерфейс1</span><span class="sxs-lookup"><span data-stu-id="71618-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="71618-103">Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="71618-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71618-104">Методы</span><span class="sxs-lookup"><span data-stu-id="71618-104">Methods</span></span>  
  
|<span data-ttu-id="71618-105">Метод</span><span class="sxs-lookup"><span data-stu-id="71618-105">Method</span></span>|<span data-ttu-id="71618-106">Описание</span><span class="sxs-lookup"><span data-stu-id="71618-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="71618-107">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="71618-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="71618-108">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="71618-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="71618-109">Continue-метод</span><span class="sxs-lookup"><span data-stu-id="71618-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="71618-110">Возобновление выполнения управляемых потоков после вызова [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="71618-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="71618-111">Detach-метод</span><span class="sxs-lookup"><span data-stu-id="71618-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="71618-112">Отсоединяет отладчик от процесса или домена приложения.</span><span class="sxs-lookup"><span data-stu-id="71618-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="71618-113">Метод EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="71618-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="71618-114">Возвращает перечислитель для активных управляемых потоков в процессе.</span><span class="sxs-lookup"><span data-stu-id="71618-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="71618-115">Метод HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="71618-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="71618-116">Возвращает значение, указывающее ли любого управляемого обратных вызовов в настоящее время в очереди для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="71618-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="71618-117">Метод IsRunning</span><span class="sxs-lookup"><span data-stu-id="71618-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="71618-118">Возвращает значение, указывающее, является ли потоки в процессе в данный момент выполнения свободно.</span><span class="sxs-lookup"><span data-stu-id="71618-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="71618-119">Метод SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="71618-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="71618-120">Задает состояние отладки все управляемые потоки в процессе.</span><span class="sxs-lookup"><span data-stu-id="71618-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="71618-121">STOP-метод</span><span class="sxs-lookup"><span data-stu-id="71618-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="71618-122">Выполняет совместную остановку всех потоков, выполняющих управляемый код в процессе.</span><span class="sxs-lookup"><span data-stu-id="71618-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="71618-123">Terminate-метод</span><span class="sxs-lookup"><span data-stu-id="71618-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="71618-124">Завершает процесс с помощью указанного кода выхода.</span><span class="sxs-lookup"><span data-stu-id="71618-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71618-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="71618-125">Remarks</span></span>  
 <span data-ttu-id="71618-126">Если `ICorDebugController` является управление процессом, включает все потоки данного процесса.</span><span class="sxs-lookup"><span data-stu-id="71618-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="71618-127">Если `ICorDebugController` — управление доменом приложения, включает только потоки данного конкретного домена приложений.</span><span class="sxs-lookup"><span data-stu-id="71618-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71618-128">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="71618-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71618-129">Требования</span><span class="sxs-lookup"><span data-stu-id="71618-129">Requirements</span></span>  
 <span data-ttu-id="71618-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71618-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71618-131">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71618-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71618-132">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71618-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71618-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71618-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71618-134">См. также</span><span class="sxs-lookup"><span data-stu-id="71618-134">See Also</span></span>  
 [<span data-ttu-id="71618-135">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="71618-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
