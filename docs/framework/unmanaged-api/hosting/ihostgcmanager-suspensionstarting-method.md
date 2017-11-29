---
title: "Метод IHostGCManager::SuspensionStarting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="fdc57-102">Метод IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="fdc57-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="fdc57-103">Уведомляет узел, что общеязыковой среды выполнения (CLR) приостановила выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fdc57-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdc57-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fdc57-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fdc57-105">Return Value</span></span>  
  
|<span data-ttu-id="fdc57-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fdc57-106">HRESULT</span></span>|<span data-ttu-id="fdc57-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fdc57-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdc57-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdc57-108">S_OK</span></span>|<span data-ttu-id="fdc57-109">`SuspensionStarting`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fdc57-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="fdc57-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fdc57-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fdc57-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fdc57-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fdc57-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fdc57-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fdc57-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="fdc57-113">The call timed out.</span></span>|  
|<span data-ttu-id="fdc57-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fdc57-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fdc57-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="fdc57-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fdc57-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fdc57-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fdc57-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="fdc57-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fdc57-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fdc57-118">E_FAIL</span></span>|<span data-ttu-id="fdc57-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="fdc57-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fdc57-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fdc57-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fdc57-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fdc57-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdc57-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="fdc57-122">Remarks</span></span>  
 <span data-ttu-id="fdc57-123">Среда CLR вызывает `SuspensionStarting` для информирования основного, сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="fdc57-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fdc57-124">Не следует перепланировать этой задачи.</span><span class="sxs-lookup"><span data-stu-id="fdc57-124">Do not reschedule this task.</span></span> <span data-ttu-id="fdc57-125">Узел должен повторно запланировать задачу при [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="fdc57-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc57-126">Требования</span><span class="sxs-lookup"><span data-stu-id="fdc57-126">Requirements</span></span>  
 <span data-ttu-id="fdc57-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdc57-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc57-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fdc57-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdc57-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdc57-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdc57-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc57-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdc57-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fdc57-131">See Also</span></span>  
 [<span data-ttu-id="fdc57-132">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fdc57-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fdc57-133">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fdc57-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fdc57-134">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fdc57-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fdc57-135">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fdc57-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="fdc57-136">IHostGCManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="fdc57-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
