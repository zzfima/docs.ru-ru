---
title: Метод ICLRDebugManager::BeginConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5938f916dfab9434c40b43fa8dfc5a1ef263db80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552883"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="4a85b-102">Метод ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="4a85b-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="4a85b-103">Устанавливает новое соединение между узлом и отладчик, чтобы связать список задач с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="4a85b-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a85b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a85b-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a85b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a85b-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="4a85b-106">[in] Идентификатор должен быть сопоставлен в списке общих задач языковой среды исполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4a85b-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="4a85b-107">[in] Понятное имя, связанное со списком задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="4a85b-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a85b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a85b-108">Return Value</span></span>  
  
|<span data-ttu-id="4a85b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a85b-109">HRESULT</span></span>|<span data-ttu-id="4a85b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4a85b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a85b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a85b-111">S_OK</span></span>|<span data-ttu-id="4a85b-112">`BeginConnection` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4a85b-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="4a85b-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a85b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a85b-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4a85b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a85b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a85b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a85b-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4a85b-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a85b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a85b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a85b-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4a85b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a85b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a85b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a85b-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4a85b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a85b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a85b-121">E_FAIL</span></span>|<span data-ttu-id="4a85b-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="4a85b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a85b-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="4a85b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a85b-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a85b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a85b-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4a85b-125">E_INVALIDARG</span></span>|<span data-ttu-id="4a85b-126">`dwConnectionId` равно нулю, или `BeginConnection` уже был вызван с помощью этого `dwConnectionId` значение, или `szConnectionName` имел значение null.</span><span class="sxs-lookup"><span data-stu-id="4a85b-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="4a85b-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a85b-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4a85b-128">Не хватает памяти может быть выделен для хранения в список задач, связанных с этим подключением.</span><span class="sxs-lookup"><span data-stu-id="4a85b-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a85b-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a85b-129">Remarks</span></span>  
 <span data-ttu-id="4a85b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), для связывания списки задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="4a85b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a85b-131">Эти три метода должен вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="4a85b-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="4a85b-132">`BeginConnection` Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="4a85b-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="4a85b-133">`SetConnectionTasks` Затем вызывается для обеспечивают набор задач, связываемое с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="4a85b-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="4a85b-134">`EndConnection` вызывается для удаления связи между списка задач, идентификатор и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="4a85b-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a85b-135">Требования</span><span class="sxs-lookup"><span data-stu-id="4a85b-135">Requirements</span></span>  
 <span data-ttu-id="4a85b-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a85b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a85b-137">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a85b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a85b-138">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a85b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a85b-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a85b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a85b-140">См. также</span><span class="sxs-lookup"><span data-stu-id="4a85b-140">See also</span></span>
- [<span data-ttu-id="4a85b-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="4a85b-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="4a85b-142">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="4a85b-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="4a85b-143">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="4a85b-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="4a85b-144">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="4a85b-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="4a85b-145">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="4a85b-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
