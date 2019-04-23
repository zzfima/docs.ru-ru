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
ms.openlocfilehash: 1d9fcbca92b1615679be57fb4c9b872339fef8a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118226"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="4481c-102">Метод IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="4481c-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="4481c-103">Вызывает текущий [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) экземпляр ждать, пока он принадлежал или заданного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="4481c-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4481c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4481c-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4481c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4481c-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="4481c-106">[in] Количество миллисекунд ожидания перед возвратом, если текущий `IHostSemaphore` экземпляр не принадлежит.</span><span class="sxs-lookup"><span data-stu-id="4481c-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="4481c-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, определяющее, какое действие должен выполнить узел, если данная операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="4481c-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4481c-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4481c-108">Return Value</span></span>  
  
|<span data-ttu-id="4481c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4481c-109">HRESULT</span></span>|<span data-ttu-id="4481c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="4481c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4481c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4481c-111">S_OK</span></span>|<span data-ttu-id="4481c-112">`Wait` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4481c-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="4481c-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4481c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4481c-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4481c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4481c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4481c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4481c-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="4481c-116">The call timed out.</span></span>|  
|<span data-ttu-id="4481c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4481c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4481c-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="4481c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4481c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4481c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4481c-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="4481c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4481c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4481c-121">E_FAIL</span></span>|<span data-ttu-id="4481c-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="4481c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4481c-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4481c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4481c-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4481c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4481c-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="4481c-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="4481c-126">Узел обнаружил взаимоблокировку в период ожидания и выберите текущий `IHostSemaphore` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="4481c-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4481c-127">Требования</span><span class="sxs-lookup"><span data-stu-id="4481c-127">Requirements</span></span>  
 <span data-ttu-id="4481c-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4481c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4481c-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4481c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4481c-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4481c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4481c-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4481c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4481c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4481c-132">See also</span></span>

- [<span data-ttu-id="4481c-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4481c-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4481c-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4481c-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="4481c-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4481c-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="4481c-136">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4481c-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="4481c-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4481c-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
