---
title: Метод IHostSemaphore::Wait
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d87243da4d68eb1ec12fda7aa62a5c4006b9729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="7a214-102">Метод IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="7a214-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="7a214-103">Вызывает текущий [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) экземпляр ожидать его признания или указанного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="7a214-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a214-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a214-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a214-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7a214-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="7a214-106">[in] Количество миллисекунд для ожидания перед возвратом, если текущий `IHostSemaphore` не является владельцем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="7a214-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="7a214-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающий, какое действие должен предпринять узел при этом операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="7a214-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a214-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7a214-108">Return Value</span></span>  
  
|<span data-ttu-id="7a214-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a214-109">HRESULT</span></span>|<span data-ttu-id="7a214-110">Описание</span><span class="sxs-lookup"><span data-stu-id="7a214-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a214-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a214-111">S_OK</span></span>|<span data-ttu-id="7a214-112">`Wait` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7a214-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="7a214-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a214-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a214-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="7a214-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a214-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a214-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a214-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="7a214-116">The call timed out.</span></span>|  
|<span data-ttu-id="7a214-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a214-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a214-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="7a214-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a214-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a214-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a214-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="7a214-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a214-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a214-121">E_FAIL</span></span>|<span data-ttu-id="7a214-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="7a214-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a214-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="7a214-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a214-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7a214-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a214-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="7a214-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="7a214-126">Узел обнаружил взаимоблокировку в период ожидания при выборе текущего `IHostSemaphore` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="7a214-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a214-127">Требования</span><span class="sxs-lookup"><span data-stu-id="7a214-127">Requirements</span></span>  
 <span data-ttu-id="7a214-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a214-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a214-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a214-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a214-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a214-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a214-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a214-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a214-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7a214-132">See Also</span></span>  
 [<span data-ttu-id="7a214-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7a214-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7a214-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="7a214-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="7a214-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7a214-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="7a214-136">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="7a214-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="7a214-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7a214-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
