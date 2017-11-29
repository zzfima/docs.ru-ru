---
title: "Метод IHostTaskManager::BeginDelayAbort"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.BeginDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17af69c533c62b6a25d498fb245dfefe162690ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="6cdc9-102">Метод IHostTaskManager::BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="6cdc9-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="6cdc9-103">Уведомляет хост, что управляемый код к периоду, в котором текущей задачи недопустимо.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cdc9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cdc9-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6cdc9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6cdc9-105">Return Value</span></span>  
  
|<span data-ttu-id="6cdc9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6cdc9-106">HRESULT</span></span>|<span data-ttu-id="6cdc9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6cdc9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6cdc9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="6cdc9-108">S_OK</span></span>|<span data-ttu-id="6cdc9-109">`BeginDelayAbort`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="6cdc9-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6cdc9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6cdc9-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6cdc9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6cdc9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6cdc9-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-113">The call timed out.</span></span>|  
|<span data-ttu-id="6cdc9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6cdc9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6cdc9-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6cdc9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6cdc9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6cdc9-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6cdc9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6cdc9-118">E_FAIL</span></span>|<span data-ttu-id="6cdc9-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6cdc9-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6cdc9-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6cdc9-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="6cdc9-122">E_UNEXPECTED</span></span>|<span data-ttu-id="6cdc9-123">`BeginDelayAbort`уже был вызван, но соответствующего вызова [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) еще не были получены.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cdc9-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6cdc9-124">Remarks</span></span>  
 <span data-ttu-id="6cdc9-125">Узел не должен прервать текущую задачу до `EndDelayAbort` вызывается.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="6cdc9-126">Если другой вызов `BeginDelayAbort` устанавливается без промежуточных вызовов `EndDelayAbort`, узел должен возвращать E_UNEXPECTED из `BeginDelayAbort`и не предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="6cdc9-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cdc9-127">Требования</span><span class="sxs-lookup"><span data-stu-id="6cdc9-127">Requirements</span></span>  
 <span data-ttu-id="6cdc9-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cdc9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cdc9-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6cdc9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6cdc9-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6cdc9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6cdc9-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cdc9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cdc9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6cdc9-132">See Also</span></span>  
 [<span data-ttu-id="6cdc9-133">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6cdc9-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6cdc9-134">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6cdc9-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6cdc9-135">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6cdc9-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="6cdc9-136">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6cdc9-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
