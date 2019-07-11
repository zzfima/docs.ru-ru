---
title: Метод IHostSemaphore::ReleaseSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e977133d722edc7d090d07cd117ee282a8d29cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753579"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="03985-102">Метод IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="03985-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="03985-103">Увеличивает счетчик текущего [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) экземпляр на указанную величину.</span><span class="sxs-lookup"><span data-stu-id="03985-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03985-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03985-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03985-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03985-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="03985-106">[in] Величина, на которое нужно увеличить число текущего `IHostSemaphore` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="03985-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="03985-107">Это значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="03985-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="03985-108">[out] Указатель на предыдущее количество, или значение null, если вызывающий объект не требует счетчика.</span><span class="sxs-lookup"><span data-stu-id="03985-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03985-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03985-109">Return Value</span></span>  
  
|<span data-ttu-id="03985-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03985-110">HRESULT</span></span>|<span data-ttu-id="03985-111">Описание</span><span class="sxs-lookup"><span data-stu-id="03985-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03985-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="03985-112">S_OK</span></span>|<span data-ttu-id="03985-113">`ReleaseSemaphore` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="03985-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="03985-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03985-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03985-115">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="03985-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03985-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03985-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03985-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="03985-117">The call timed out.</span></span>|  
|<span data-ttu-id="03985-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03985-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03985-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="03985-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03985-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03985-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03985-121">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="03985-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03985-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03985-122">E_FAIL</span></span>|<span data-ttu-id="03985-123">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="03985-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03985-124">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="03985-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03985-125">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03985-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03985-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="03985-126">Remarks</span></span>  
 <span data-ttu-id="03985-127">Среда CLR обычно вызывает `ReleaseSemaphore` для уведомления узла о завершении использования ресурсов, передавая значение 1 для `lReleaseCount` параметра.</span><span class="sxs-lookup"><span data-stu-id="03985-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03985-128">Требования</span><span class="sxs-lookup"><span data-stu-id="03985-128">Requirements</span></span>  
 <span data-ttu-id="03985-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03985-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03985-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03985-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03985-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03985-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03985-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03985-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03985-133">См. также</span><span class="sxs-lookup"><span data-stu-id="03985-133">See also</span></span>

- [<span data-ttu-id="03985-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="03985-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="03985-135">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="03985-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="03985-136">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="03985-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="03985-137">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="03985-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="03985-138">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="03985-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
