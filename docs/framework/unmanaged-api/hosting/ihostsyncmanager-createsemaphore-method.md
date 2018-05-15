---
title: Метод IHostSyncManager::CreateSemaphore
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 003e385ade6357b76823986d20e8fdf3d4c3757f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="a0147-102">Метод IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="a0147-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="a0147-103">Создает [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) объект для среды (CLR) в качестве семафор для ожидания события.</span><span class="sxs-lookup"><span data-stu-id="a0147-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0147-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0147-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0147-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0147-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="a0147-106">[in] Исходное значение счетчика `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="a0147-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="a0147-107">[in] Максимальное количество для `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="a0147-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="a0147-108">[out] Указатель на адрес `IHostSemaphore` экземпляра, или значение null, если не удалось создать семафор.</span><span class="sxs-lookup"><span data-stu-id="a0147-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0147-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0147-109">Return Value</span></span>  
  
|<span data-ttu-id="a0147-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0147-110">HRESULT</span></span>|<span data-ttu-id="a0147-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a0147-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0147-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0147-112">S_OK</span></span>|<span data-ttu-id="a0147-113">`CreateSemaphore` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a0147-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="a0147-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0147-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0147-115">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0147-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0147-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0147-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0147-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a0147-117">The call timed out.</span></span>|  
|<span data-ttu-id="a0147-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0147-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0147-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a0147-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0147-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0147-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0147-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a0147-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0147-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0147-122">E_FAIL</span></span>|<span data-ttu-id="a0147-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0147-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0147-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0147-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0147-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0147-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0147-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a0147-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a0147-127">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="a0147-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0147-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0147-128">Remarks</span></span>  
 <span data-ttu-id="a0147-129">`CreateSemaphore` функция зеркал Win32, которая имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="a0147-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="a0147-130">`dwInitial` И `dwMax` параметров служит ту же семантику для счетчика семафора Win32 `lInitialCount` и `lMaximumCount` параметров, соответственно.</span><span class="sxs-lookup"><span data-stu-id="a0147-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="a0147-131">`dwInitial` должно быть в диапазоне от нуля и `dwMax`включительно.</span><span class="sxs-lookup"><span data-stu-id="a0147-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="a0147-132">`dwMax` Должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="a0147-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0147-133">Требования</span><span class="sxs-lookup"><span data-stu-id="a0147-133">Requirements</span></span>  
 <span data-ttu-id="a0147-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0147-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0147-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0147-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0147-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0147-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0147-137">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0147-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0147-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a0147-138">See Also</span></span>  
 [<span data-ttu-id="a0147-139">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0147-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="a0147-140">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a0147-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="a0147-141">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0147-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
