---
title: Метод ICLRDebugManager::EndConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf21e1844ea99b231054f8350ddacb8bb707a94e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969875"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="89b5b-102">Метод ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="89b5b-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="89b5b-103">Удаляет связь между список задач и идентификатора и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="89b5b-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89b5b-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89b5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89b5b-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="89b5b-106">[in] Идентификатор конкретного узла для подключения и связанный список общих задач языковой среды исполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="89b5b-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89b5b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="89b5b-107">Return Value</span></span>  
  
|<span data-ttu-id="89b5b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89b5b-108">HRESULT</span></span>|<span data-ttu-id="89b5b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="89b5b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89b5b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="89b5b-110">S_OK</span></span>|<span data-ttu-id="89b5b-111">`EndConnection` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="89b5b-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="89b5b-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89b5b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89b5b-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="89b5b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89b5b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89b5b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89b5b-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="89b5b-115">The call timed out.</span></span>|  
|<span data-ttu-id="89b5b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89b5b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89b5b-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="89b5b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89b5b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89b5b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89b5b-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="89b5b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89b5b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89b5b-120">E_FAIL</span></span>|<span data-ttu-id="89b5b-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="89b5b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89b5b-122">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="89b5b-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89b5b-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89b5b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="89b5b-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="89b5b-124">E_INVALIDARG</span></span>|<span data-ttu-id="89b5b-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) никогда не был вызван с помощью `dwConnectionId`, или `dwConnectionId` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="89b5b-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b5b-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="89b5b-126">Remarks</span></span>  
 <span data-ttu-id="89b5b-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), и `EndConnection`, для связывания списки задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="89b5b-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89b5b-128">Эти три метода должен вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="89b5b-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="89b5b-129">`BeginConnection` Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="89b5b-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="89b5b-130">`SetConnectionTasks` Затем вызывается для обеспечивают набор задач, связываемое с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="89b5b-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="89b5b-131">`EndConnection` вызывается для удаления связи между списка задач, идентификатор и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="89b5b-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89b5b-132">Требования</span><span class="sxs-lookup"><span data-stu-id="89b5b-132">Requirements</span></span>  
 <span data-ttu-id="89b5b-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89b5b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89b5b-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89b5b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89b5b-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89b5b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89b5b-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89b5b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b5b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="89b5b-137">See also</span></span>

- [<span data-ttu-id="89b5b-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="89b5b-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="89b5b-139">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="89b5b-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="89b5b-140">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="89b5b-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="89b5b-141">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="89b5b-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="89b5b-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="89b5b-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
