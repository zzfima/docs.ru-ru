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
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133995"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="3cfd3-102">Метод ICLRDebugManager::BeginConnection</span><span class="sxs-lookup"><span data-stu-id="3cfd3-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="3cfd3-103">Устанавливает новое соединение между узлом и отладчик, чтобы связать список задач с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfd3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cfd3-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cfd3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cfd3-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="3cfd3-106">[in] Идентификатор должен быть сопоставлен в списке общих задач языковой среды исполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="3cfd3-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="3cfd3-107">[in] Понятное имя, связанное со списком задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cfd3-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3cfd3-108">Return Value</span></span>  
  
|<span data-ttu-id="3cfd3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cfd3-109">HRESULT</span></span>|<span data-ttu-id="3cfd3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3cfd3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cfd3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cfd3-111">S_OK</span></span>|`BeginConnection` <span data-ttu-id="3cfd3-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-112">returned successfully.</span></span>|  
|<span data-ttu-id="3cfd3-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cfd3-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cfd3-114">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3cfd3-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3cfd3-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3cfd3-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-116">The call timed out.</span></span>|  
|<span data-ttu-id="3cfd3-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3cfd3-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3cfd3-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3cfd3-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3cfd3-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3cfd3-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3cfd3-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cfd3-121">E_FAIL</span></span>|<span data-ttu-id="3cfd3-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3cfd3-123">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3cfd3-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3cfd3-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3cfd3-125">E_INVALIDARG</span></span>|`dwConnectionId` <span data-ttu-id="3cfd3-126">равно нулю, или `BeginConnection` уже был вызван с помощью этого `dwConnectionId` значение, или `szConnectionName` имел значение null.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-126">was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="3cfd3-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3cfd3-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3cfd3-128">Не хватает памяти может быть выделен для хранения в список задач, связанных с этим подключением.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cfd3-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="3cfd3-129">Remarks</span></span>  
 <span data-ttu-id="3cfd3-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), для связывания списки задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cfd3-131">Эти три метода должен вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-131">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="3cfd3-132">Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-132">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="3cfd3-133">Затем вызывается для обеспечивают набор задач, связываемое с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-133">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="3cfd3-134">вызывается для удаления связи между списка задач, идентификатор и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="3cfd3-134">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfd3-135">Требования</span><span class="sxs-lookup"><span data-stu-id="3cfd3-135">Requirements</span></span>  
 <span data-ttu-id="3cfd3-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfd3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfd3-137">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3cfd3-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cfd3-138">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cfd3-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3cfd3-139">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3cfd3-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cfd3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="3cfd3-140">See also</span></span>

- [<span data-ttu-id="3cfd3-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3cfd3-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3cfd3-142">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="3cfd3-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="3cfd3-143">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="3cfd3-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="3cfd3-144">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="3cfd3-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="3cfd3-145">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="3cfd3-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
