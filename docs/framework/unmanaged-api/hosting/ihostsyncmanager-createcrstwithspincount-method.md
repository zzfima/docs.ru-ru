---
title: "Метод IHostSyncManager::CreateCrstWithSpinCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41031a5e3d423f0c1d7459250073634592e0291e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="c5f3f-102">Метод IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="c5f3f-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="c5f3f-103">Создает объект критической секции с прокруток для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f3f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5f3f-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5f3f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5f3f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="c5f3f-106">[in] Задает счетчик прокруток для объекта критической секции.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="c5f3f-107">[out] Указатель на адрес [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра, или значение null, если не удалось создать критической секции.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5f3f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5f3f-108">Return Value</span></span>  
  
|<span data-ttu-id="c5f3f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5f3f-109">HRESULT</span></span>|<span data-ttu-id="c5f3f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c5f3f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5f3f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5f3f-111">S_OK</span></span>|<span data-ttu-id="c5f3f-112">`CreateCrstWithSpinCount`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="c5f3f-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5f3f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5f3f-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5f3f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5f3f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5f3f-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-116">The call timed out.</span></span>|  
|<span data-ttu-id="c5f3f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5f3f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5f3f-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5f3f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5f3f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5f3f-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5f3f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5f3f-121">E_FAIL</span></span>|<span data-ttu-id="c5f3f-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5f3f-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5f3f-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c5f3f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c5f3f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c5f3f-126">Не хватает памяти была доступна для создания запрошенной критической секции.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f3f-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5f3f-127">Remarks</span></span>  
 <span data-ttu-id="c5f3f-128">Счетчик прокруток используется только в системе с несколькими процессорами.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="c5f3f-129">Счетчик прокруток указывает количество раз, когда вызывающий поток должен выполнить перед выполнением операции ожидания в семафор, который связан с недоступной критической секцией.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="c5f3f-130">Если критическая секция освобождается во время операции прокрутки, вызывающий поток позволяет избежать ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="c5f3f-131">`CreateCrstWithSpinCount`зеркально отражает Win32 `InitializeCriticalSectionAndSpinCount` функции.</span><span class="sxs-lookup"><span data-stu-id="c5f3f-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5f3f-132">Требования</span><span class="sxs-lookup"><span data-stu-id="c5f3f-132">Requirements</span></span>  
 <span data-ttu-id="c5f3f-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5f3f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5f3f-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c5f3f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5f3f-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5f3f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5f3f-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5f3f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f3f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f3f-137">See Also</span></span>  
 [<span data-ttu-id="c5f3f-138">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c5f3f-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c5f3f-139">IHostSemaphore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c5f3f-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="c5f3f-140">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c5f3f-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
