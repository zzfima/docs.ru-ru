---
title: "Метод IHostSyncManager::CreateSemaphore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c7e33e4f178a4fd51ae27912959d0e4edf30ecb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="dfc27-102">Метод IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="dfc27-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="dfc27-103">Создает [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) объект для среды (CLR) в качестве семафор для ожидания события.</span><span class="sxs-lookup"><span data-stu-id="dfc27-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfc27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dfc27-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfc27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dfc27-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="dfc27-106">[in] Исходное значение счетчика `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="dfc27-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="dfc27-107">[in] Максимальное количество для `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="dfc27-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="dfc27-108">[out] Указатель на адрес `IHostSemaphore` экземпляра, или значение null, если не удалось создать семафор.</span><span class="sxs-lookup"><span data-stu-id="dfc27-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dfc27-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dfc27-109">Return Value</span></span>  
  
|<span data-ttu-id="dfc27-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dfc27-110">HRESULT</span></span>|<span data-ttu-id="dfc27-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dfc27-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dfc27-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="dfc27-112">S_OK</span></span>|<span data-ttu-id="dfc27-113">`CreateSemaphore`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dfc27-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="dfc27-114">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dfc27-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dfc27-115">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dfc27-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dfc27-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dfc27-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dfc27-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="dfc27-117">The call timed out.</span></span>|  
|<span data-ttu-id="dfc27-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dfc27-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dfc27-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="dfc27-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dfc27-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dfc27-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dfc27-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="dfc27-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dfc27-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dfc27-122">E_FAIL</span></span>|<span data-ttu-id="dfc27-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="dfc27-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dfc27-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dfc27-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dfc27-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dfc27-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dfc27-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dfc27-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dfc27-127">Не хватает памяти была доступна для создания запрошенного объекта события.</span><span class="sxs-lookup"><span data-stu-id="dfc27-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dfc27-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="dfc27-128">Remarks</span></span>  
 <span data-ttu-id="dfc27-129">`CreateSemaphore`функция зеркал Win32, которая имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="dfc27-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="dfc27-130">`dwInitial` И `dwMax` параметров служит ту же семантику для счетчика семафора Win32 `lInitialCount` и `lMaximumCount` параметров, соответственно.</span><span class="sxs-lookup"><span data-stu-id="dfc27-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="dfc27-131">`dwInitial`должно быть в диапазоне от нуля и `dwMax`включительно.</span><span class="sxs-lookup"><span data-stu-id="dfc27-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="dfc27-132">`dwMax`должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="dfc27-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfc27-133">Требования</span><span class="sxs-lookup"><span data-stu-id="dfc27-133">Requirements</span></span>  
 <span data-ttu-id="dfc27-134">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfc27-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfc27-135">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dfc27-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfc27-136">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dfc27-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dfc27-137">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfc27-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc27-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dfc27-138">See Also</span></span>  
 [<span data-ttu-id="dfc27-139">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dfc27-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="dfc27-140">IHostSemaphore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dfc27-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="dfc27-141">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dfc27-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
