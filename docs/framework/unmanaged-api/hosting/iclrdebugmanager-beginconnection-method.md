---
title: "Метод ICLRDebugManager::BeginConnection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.BeginConnection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 302b2abfdde7bbccbef51de21233948d042420be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="8ef27-102">Метод ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="8ef27-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="8ef27-103">Устанавливает новое соединение между узлом и отладчик, чтобы связать список задач с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="8ef27-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ef27-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ef27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8ef27-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="8ef27-106">[in] Идентификатор для связи с список общих задач языка среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8ef27-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="8ef27-107">[in] Понятное имя, связанное со списком задач со средой CLR.</span><span class="sxs-lookup"><span data-stu-id="8ef27-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef27-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8ef27-108">Return Value</span></span>  
  
|<span data-ttu-id="8ef27-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ef27-109">HRESULT</span></span>|<span data-ttu-id="8ef27-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8ef27-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ef27-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ef27-111">S_OK</span></span>|<span data-ttu-id="8ef27-112">`BeginConnection`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8ef27-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="8ef27-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ef27-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ef27-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8ef27-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ef27-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ef27-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ef27-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8ef27-116">The call timed out.</span></span>|  
|<span data-ttu-id="8ef27-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ef27-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ef27-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8ef27-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ef27-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ef27-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ef27-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8ef27-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ef27-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ef27-121">E_FAIL</span></span>|<span data-ttu-id="8ef27-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8ef27-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ef27-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8ef27-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ef27-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ef27-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ef27-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8ef27-125">E_INVALIDARG</span></span>|<span data-ttu-id="8ef27-126">`dwConnectionId`равно нулю, или `BeginConnection` уже был вызван с помощью этого `dwConnectionId` значение, или `szConnectionName` имел значение null.</span><span class="sxs-lookup"><span data-stu-id="8ef27-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="8ef27-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ef27-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8ef27-128">Не хватает памяти может быть выделен для размещения в список задач, связанных с этим подключением.</span><span class="sxs-lookup"><span data-stu-id="8ef27-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ef27-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ef27-129">Remarks</span></span>  
 <span data-ttu-id="8ef27-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), для связывания списки задач с идентификаторы и понятные имена.</span><span class="sxs-lookup"><span data-stu-id="8ef27-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ef27-131">Эти три метода вызываются в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="8ef27-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="8ef27-132">`BeginConnection`Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="8ef27-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="8ef27-133">`SetConnectionTasks`вызывается Далее необходимо предоставить набор задач, которые необходимо связать с подключением.</span><span class="sxs-lookup"><span data-stu-id="8ef27-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="8ef27-134">`EndConnection`вызывается для удаления связи между списком задач и идентификатором и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="8ef27-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef27-135">Требования</span><span class="sxs-lookup"><span data-stu-id="8ef27-135">Requirements</span></span>  
 <span data-ttu-id="8ef27-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ef27-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef27-137">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ef27-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ef27-138">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8ef27-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef27-139">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef27-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef27-140">См. также</span><span class="sxs-lookup"><span data-stu-id="8ef27-140">See Also</span></span>  
 [<span data-ttu-id="8ef27-141">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ef27-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8ef27-142">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ef27-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="8ef27-143">EndConnection-метод</span><span class="sxs-lookup"><span data-stu-id="8ef27-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="8ef27-144">SetConnectionTasks-метод</span><span class="sxs-lookup"><span data-stu-id="8ef27-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="8ef27-145">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8ef27-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
