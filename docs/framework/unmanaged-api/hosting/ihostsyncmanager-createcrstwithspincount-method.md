---
title: Метод IHostSyncManager::CreateCrstWithSpinCount
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a288edc89029804de277484741c1895af7859b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081532"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="3b977-102">Метод IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="3b977-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="3b977-103">Создает объект критической секции с числом прокруток для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="3b977-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b977-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b977-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b977-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b977-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="3b977-106">[in] Задает счетчик прокруток для объекта критической секции.</span><span class="sxs-lookup"><span data-stu-id="3b977-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="3b977-107">[out] Указатель на адрес [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра, или значение null, если не удалось создать критический раздел.</span><span class="sxs-lookup"><span data-stu-id="3b977-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b977-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3b977-108">Return Value</span></span>  
  
|<span data-ttu-id="3b977-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b977-109">HRESULT</span></span>|<span data-ttu-id="3b977-110">Описание</span><span class="sxs-lookup"><span data-stu-id="3b977-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b977-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b977-111">S_OK</span></span>|`CreateCrstWithSpinCount` <span data-ttu-id="3b977-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3b977-112">returned successfully.</span></span>|  
|<span data-ttu-id="3b977-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b977-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b977-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3b977-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3b977-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3b977-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3b977-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3b977-116">The call timed out.</span></span>|  
|<span data-ttu-id="3b977-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3b977-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3b977-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3b977-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3b977-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3b977-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3b977-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3b977-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3b977-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b977-121">E_FAIL</span></span>|<span data-ttu-id="3b977-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3b977-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3b977-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3b977-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3b977-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3b977-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3b977-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3b977-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3b977-126">Недостаточно памяти, доступного для создания запрошенной критической секции.</span><span class="sxs-lookup"><span data-stu-id="3b977-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b977-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b977-127">Remarks</span></span>  
 <span data-ttu-id="3b977-128">Счетчик прокруток используется только в многопроцессорной системе.</span><span class="sxs-lookup"><span data-stu-id="3b977-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="3b977-129">Счетчик прокруток указывает количество раз, когда вызывающий поток должен выполнить перед выполнением операции ожидания для семафора, связанный с недоступной критической секцией.</span><span class="sxs-lookup"><span data-stu-id="3b977-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="3b977-130">Если во время операции управления "Счетчик" критический раздел стал доступным, вызывающий поток позволяет избежать операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="3b977-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> `CreateCrstWithSpinCount` <span data-ttu-id="3b977-131">зеркально отражает Win32 `InitializeCriticalSectionAndSpinCount` функции.</span><span class="sxs-lookup"><span data-stu-id="3b977-131">mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b977-132">Требования</span><span class="sxs-lookup"><span data-stu-id="3b977-132">Requirements</span></span>  
 <span data-ttu-id="3b977-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b977-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b977-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b977-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b977-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b977-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3b977-136">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b977-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b977-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3b977-137">See also</span></span>

- [<span data-ttu-id="3b977-138">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3b977-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3b977-139">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="3b977-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="3b977-140">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3b977-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
