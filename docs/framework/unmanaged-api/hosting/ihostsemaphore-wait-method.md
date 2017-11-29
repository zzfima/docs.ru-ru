---
title: "Метод IHostSemaphore::Wait"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d30a946cadc312e683d256ce6f08528cffa95481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="372e9-102">Метод IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="372e9-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="372e9-103">Вызывает текущий [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) экземпляр ожидать его признания или указанного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="372e9-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372e9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="372e9-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="372e9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="372e9-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="372e9-106">[in] Количество миллисекунд для ожидания перед возвратом, если текущий `IHostSemaphore` не является владельцем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="372e9-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="372e9-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающий, какое действие должен предпринять узел при этом операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="372e9-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="372e9-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="372e9-108">Return Value</span></span>  
  
|<span data-ttu-id="372e9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="372e9-109">HRESULT</span></span>|<span data-ttu-id="372e9-110">Описание</span><span class="sxs-lookup"><span data-stu-id="372e9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="372e9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="372e9-111">S_OK</span></span>|<span data-ttu-id="372e9-112">`Wait`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="372e9-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="372e9-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="372e9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="372e9-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="372e9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="372e9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="372e9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="372e9-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="372e9-116">The call timed out.</span></span>|  
|<span data-ttu-id="372e9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="372e9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="372e9-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="372e9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="372e9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="372e9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="372e9-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="372e9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="372e9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="372e9-121">E_FAIL</span></span>|<span data-ttu-id="372e9-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="372e9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="372e9-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="372e9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="372e9-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="372e9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="372e9-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="372e9-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="372e9-126">Узел обнаружил взаимоблокировку в период ожидания при выборе текущего `IHostSemaphore` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="372e9-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="372e9-127">Требования</span><span class="sxs-lookup"><span data-stu-id="372e9-127">Requirements</span></span>  
 <span data-ttu-id="372e9-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="372e9-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="372e9-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="372e9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="372e9-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="372e9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="372e9-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="372e9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372e9-132">См. также</span><span class="sxs-lookup"><span data-stu-id="372e9-132">See Also</span></span>  
 [<span data-ttu-id="372e9-133">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="372e9-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="372e9-134">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="372e9-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="372e9-135">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="372e9-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="372e9-136">IHostSemaphore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="372e9-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="372e9-137">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="372e9-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
