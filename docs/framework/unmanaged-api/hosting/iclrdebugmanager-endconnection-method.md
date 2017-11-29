---
title: "Метод ICLRDebugManager::EndConnection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.EndConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 114f2217d22fc270b03d271db4acc44f0edbcca8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="1400f-102">Метод ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="1400f-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="1400f-103">Удаляет связь между список задач и идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="1400f-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1400f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1400f-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1400f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1400f-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="1400f-106">[in] Идентификатор конкретного узла для подключения и связанного списка общих задач языка среды CLR.</span><span class="sxs-lookup"><span data-stu-id="1400f-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1400f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1400f-107">Return Value</span></span>  
  
|<span data-ttu-id="1400f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1400f-108">HRESULT</span></span>|<span data-ttu-id="1400f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1400f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1400f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1400f-110">S_OK</span></span>|<span data-ttu-id="1400f-111">`EndConnection`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1400f-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="1400f-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1400f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1400f-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1400f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1400f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1400f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1400f-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1400f-115">The call timed out.</span></span>|  
|<span data-ttu-id="1400f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1400f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1400f-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1400f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1400f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1400f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1400f-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1400f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1400f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1400f-120">E_FAIL</span></span>|<span data-ttu-id="1400f-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="1400f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1400f-122">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1400f-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1400f-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1400f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1400f-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1400f-124">E_INVALIDARG</span></span>|<span data-ttu-id="1400f-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) никогда не был вызван с помощью `dwConnectionId`, или `dwConnectionId` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="1400f-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1400f-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="1400f-126">Remarks</span></span>  
 <span data-ttu-id="1400f-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и `EndConnection`, для связывания списки задач с идентификаторы и понятные имена.</span><span class="sxs-lookup"><span data-stu-id="1400f-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1400f-128">Эти три метода вызываются в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="1400f-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="1400f-129">`BeginConnection`Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="1400f-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="1400f-130">`SetConnectionTasks`вызывается Далее необходимо предоставить набор задач, которые необходимо связать с подключением.</span><span class="sxs-lookup"><span data-stu-id="1400f-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="1400f-131">`EndConnection`вызывается для удаления связи между списком задач и идентификатором и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="1400f-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1400f-132">Требования</span><span class="sxs-lookup"><span data-stu-id="1400f-132">Requirements</span></span>  
 <span data-ttu-id="1400f-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1400f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1400f-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1400f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1400f-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1400f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1400f-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1400f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1400f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="1400f-137">See Also</span></span>  
 [<span data-ttu-id="1400f-138">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1400f-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="1400f-139">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1400f-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="1400f-140">Beginconnection-метод</span><span class="sxs-lookup"><span data-stu-id="1400f-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="1400f-141">SetConnectionTasks-метод</span><span class="sxs-lookup"><span data-stu-id="1400f-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="1400f-142">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1400f-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
