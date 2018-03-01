---
title: "Метод IHostGCManager::SuspensionEnding"
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
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9660a0aa755e297721679bcf6db798384f12abd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="652b1-102">Метод IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="652b1-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="652b1-103">Уведомляет узел, что общеязыковой среды выполнения (CLR) возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="652b1-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="652b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="652b1-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="652b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="652b1-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="652b1-106">[in] Создание сборки мусора, просто завершается, из которого поток возобновляется.</span><span class="sxs-lookup"><span data-stu-id="652b1-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="652b1-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="652b1-107">Return Value</span></span>  
  
|<span data-ttu-id="652b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="652b1-108">HRESULT</span></span>|<span data-ttu-id="652b1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="652b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="652b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="652b1-110">S_OK</span></span>|<span data-ttu-id="652b1-111">`SuspensionEnding`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="652b1-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="652b1-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="652b1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="652b1-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="652b1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="652b1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="652b1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="652b1-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="652b1-115">The call timed out.</span></span>|  
|<span data-ttu-id="652b1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="652b1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="652b1-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="652b1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="652b1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="652b1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="652b1-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="652b1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="652b1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="652b1-120">E_FAIL</span></span>|<span data-ttu-id="652b1-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="652b1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="652b1-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="652b1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="652b1-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="652b1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="652b1-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="652b1-124">Remarks</span></span>  
 <span data-ttu-id="652b1-125">Среда CLR вызывает `SuspensionEnding` после его выполнения сборки мусора для информирования основного поток возобновляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="652b1-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="652b1-126">Не следует перепланировать поток, который был выполнен вызов метода из.</span><span class="sxs-lookup"><span data-stu-id="652b1-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="652b1-127">Требования</span><span class="sxs-lookup"><span data-stu-id="652b1-127">Requirements</span></span>  
 <span data-ttu-id="652b1-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="652b1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="652b1-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="652b1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="652b1-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="652b1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="652b1-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="652b1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="652b1-132">См. также</span><span class="sxs-lookup"><span data-stu-id="652b1-132">See Also</span></span>  
 [<span data-ttu-id="652b1-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="652b1-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="652b1-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="652b1-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="652b1-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="652b1-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="652b1-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="652b1-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="652b1-137">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="652b1-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
