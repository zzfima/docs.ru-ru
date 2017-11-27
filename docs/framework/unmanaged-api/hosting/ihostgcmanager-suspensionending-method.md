---
title: "Метод IHostGCManager::SuspensionEnding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9952e62d4979efa0d07b19f183ca71adcc643365
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="0beee-102">Метод IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="0beee-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="0beee-103">Уведомляет узел, что общеязыковой среды выполнения (CLR) возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0beee-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0beee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0beee-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0beee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0beee-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="0beee-106">[in] Создание сборки мусора, просто завершается, из которого поток возобновляется.</span><span class="sxs-lookup"><span data-stu-id="0beee-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0beee-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0beee-107">Return Value</span></span>  
  
|<span data-ttu-id="0beee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0beee-108">HRESULT</span></span>|<span data-ttu-id="0beee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0beee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0beee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0beee-110">S_OK</span></span>|<span data-ttu-id="0beee-111">`SuspensionEnding`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0beee-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="0beee-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0beee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0beee-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0beee-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0beee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0beee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0beee-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0beee-115">The call timed out.</span></span>|  
|<span data-ttu-id="0beee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0beee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0beee-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0beee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0beee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0beee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0beee-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0beee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0beee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0beee-120">E_FAIL</span></span>|<span data-ttu-id="0beee-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0beee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0beee-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0beee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0beee-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0beee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0beee-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0beee-124">Remarks</span></span>  
 <span data-ttu-id="0beee-125">Среда CLR вызывает `SuspensionEnding` после его выполнения сборки мусора для информирования основного поток возобновляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="0beee-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0beee-126">Не следует перепланировать поток, который был выполнен вызов метода из.</span><span class="sxs-lookup"><span data-stu-id="0beee-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0beee-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0beee-127">Requirements</span></span>  
 <span data-ttu-id="0beee-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0beee-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0beee-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0beee-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0beee-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0beee-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0beee-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0beee-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0beee-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0beee-132">See Also</span></span>  
 [<span data-ttu-id="0beee-133">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0beee-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0beee-134">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0beee-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0beee-135">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0beee-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0beee-136">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0beee-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="0beee-137">IHostGCManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0beee-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
