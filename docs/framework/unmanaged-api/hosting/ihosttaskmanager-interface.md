---
title: "Интерфейс IHostTaskManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9573891a2c27a2a92eccd0522f84175effa8037a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="f0c9a-102">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f0c9a-102">IHostTaskManager Interface</span></span>
<span data-ttu-id="f0c9a-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для работы с задачами через узел, вместо того чтобы использовать функции работы с потоками или волокон стандартной операционной системе.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-103">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0c9a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f0c9a-104">Methods</span></span>  
  
|<span data-ttu-id="f0c9a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f0c9a-105">Method</span></span>|<span data-ttu-id="f0c9a-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f0c9a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0c9a-107">Метод BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="f0c9a-107">BeginDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="f0c9a-108">Уведомляет хост, что управляемый код к периоду, в котором текущей задачи недопустимо.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-108">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="f0c9a-109">Метод BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f0c9a-109">BeginThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="f0c9a-110">Уведомляет хост, что управляемый код к периоду, в котором текущую задачу нельзя перемещать в другой поток операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-110">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="f0c9a-111">Метод CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="f0c9a-111">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="f0c9a-112">Ведущее приложение может указать, сможет ли среда вводить заданный вызов в неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-112">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="f0c9a-113">Метод CreateTask</span><span class="sxs-lookup"><span data-stu-id="f0c9a-113">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|<span data-ttu-id="f0c9a-114">Запросы на создание новой задачи.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-114">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="f0c9a-115">Метод EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="f0c9a-115">EndDelayAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="f0c9a-116">Уведомляет хост, что управляемый код завершается из-за период, в котором текущей задачи недопустимо, после любого вызова для `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-116">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="f0c9a-117">Метод EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f0c9a-117">EndThreadAffinity Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="f0c9a-118">Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы после предыдущего вызова для `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-118">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="f0c9a-119">Метод EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="f0c9a-119">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="f0c9a-120">Уведомляет основное приложение, вызов неуправляемого метода, такие как неуправляемого метода возвращает управление выполнением в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-120">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="f0c9a-121">Метод GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="f0c9a-121">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="f0c9a-122">Получает указатель интерфейса на задачу, которая в данный момент в потоке операционной системы, из которого этот вызов.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-122">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="f0c9a-123">Метод GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="f0c9a-123">GetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="f0c9a-124">Возвращает объем места в стеке, гарантированно будут доступны после завершения операций в стеке, но до закрытия процесса.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-124">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="f0c9a-125">Метод LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="f0c9a-125">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="f0c9a-126">Уведомляет хост, что управляемый код является вызова неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-126">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="f0c9a-127">Метод ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="f0c9a-127">ReverseEnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="f0c9a-128">Уведомляет узел, что вызов в среде (CLR) из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-128">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="f0c9a-129">Метод ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="f0c9a-129">ReverseLeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="f0c9a-130">Уведомляет основное приложение, что элемент управления средой CLR и неуправляемой функции, которая, в свою очередь, была вызвана из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-130">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="f0c9a-131">Метод SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f0c9a-131">SetCLRTaskManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="f0c9a-132">Предоставляет основному указатель интерфейса [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) экземпляра, реализуемых средой CLR.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-132">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="f0c9a-133">Метод SetLocale</span><span class="sxs-lookup"><span data-stu-id="f0c9a-133">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="f0c9a-134">Уведомляет узел, что среда CLR изменила языковой стандарт для текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-134">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="f0c9a-135">Метод SetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="f0c9a-135">SetStackGuarantee Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="f0c9a-136">Зарезервировано только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-136">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="f0c9a-137">Метод SetUILocale</span><span class="sxs-lookup"><span data-stu-id="f0c9a-137">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="f0c9a-138">Уведомляет основное приложение, что язык интерфейса пользователя был изменен для текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-138">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="f0c9a-139">Метод Sleep</span><span class="sxs-lookup"><span data-stu-id="f0c9a-139">Sleep Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|<span data-ttu-id="f0c9a-140">Уведомляет основное приложение, текущая задача будет в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-140">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="f0c9a-141">Метод SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="f0c9a-141">SwitchToTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="f0c9a-142">Уведомляет узел, что необходимости отключения текущей задачи.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-142">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0c9a-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0c9a-143">Remarks</span></span>  
 <span data-ttu-id="f0c9a-144">`IHostTaskManager`позволяет среде CLR создавать задачи и управлять ими, чтобы обеспечить обработчиков предпринять действия при передаче управления из управляемого в неуправляемый код и обратно, а также указать определенные действия узла может и не может принимать во время выполнения кода.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-144">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c9a-145">Требования</span><span class="sxs-lookup"><span data-stu-id="f0c9a-145">Requirements</span></span>  
 <span data-ttu-id="f0c9a-146">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c9a-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c9a-147">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0c9a-147">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0c9a-148">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0c9a-148">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0c9a-149">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c9a-149">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c9a-150">См. также</span><span class="sxs-lookup"><span data-stu-id="f0c9a-150">See Also</span></span>  
 [<span data-ttu-id="f0c9a-151">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f0c9a-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f0c9a-152">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f0c9a-152">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f0c9a-153">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="f0c9a-153">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f0c9a-154">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f0c9a-154">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
