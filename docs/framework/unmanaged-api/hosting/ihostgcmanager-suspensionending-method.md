---
title: Метод IHostGCManager::SuspensionEnding
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1995321e8598d010188fee2437640b4489eaa294
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472035"
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="57079-102">Метод IHostGCManager::SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="57079-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="57079-103">Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="57079-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57079-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57079-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57079-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57079-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="57079-106">[in] Поколении сборки мусора, просто завершается, из которого поток возобновляет работу.</span><span class="sxs-lookup"><span data-stu-id="57079-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57079-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57079-107">Return Value</span></span>  
  
|<span data-ttu-id="57079-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57079-108">HRESULT</span></span>|<span data-ttu-id="57079-109">Описание</span><span class="sxs-lookup"><span data-stu-id="57079-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57079-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="57079-110">S_OK</span></span>|<span data-ttu-id="57079-111">`SuspensionEnding` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="57079-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="57079-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57079-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57079-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="57079-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57079-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57079-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57079-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="57079-115">The call timed out.</span></span>|  
|<span data-ttu-id="57079-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57079-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57079-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="57079-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57079-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57079-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57079-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="57079-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57079-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57079-120">E_FAIL</span></span>|<span data-ttu-id="57079-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="57079-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57079-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="57079-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57079-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57079-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57079-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="57079-124">Remarks</span></span>  
 <span data-ttu-id="57079-125">Среда CLR вызывает `SuspensionEnding` после его выполнения сборки мусора, чтобы сообщить узла о том, что поток возобновляет выполнение.</span><span class="sxs-lookup"><span data-stu-id="57079-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57079-126">Не следует перепланировать обсуждение, на которое вызов метода был сделан из.</span><span class="sxs-lookup"><span data-stu-id="57079-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57079-127">Требования</span><span class="sxs-lookup"><span data-stu-id="57079-127">Requirements</span></span>  
 <span data-ttu-id="57079-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57079-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57079-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="57079-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57079-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57079-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57079-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57079-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57079-132">См. также</span><span class="sxs-lookup"><span data-stu-id="57079-132">See also</span></span>
- [<span data-ttu-id="57079-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="57079-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="57079-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="57079-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="57079-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="57079-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="57079-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="57079-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="57079-137">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="57079-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
