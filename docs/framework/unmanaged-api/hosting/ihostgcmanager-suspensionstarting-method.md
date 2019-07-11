---
title: Метод IHostGCManager::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00322a75c4a15e42c89ff5a8680171a168a37613
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758693"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="244b0-102">Метод IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="244b0-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="244b0-103">Уведомляет основное приложение, что общеязыковая среда выполнения (CLR) приостановила выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="244b0-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="244b0-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="244b0-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="244b0-105">Return Value</span></span>  
  
|<span data-ttu-id="244b0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="244b0-106">HRESULT</span></span>|<span data-ttu-id="244b0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="244b0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="244b0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="244b0-108">S_OK</span></span>|<span data-ttu-id="244b0-109">`SuspensionStarting` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="244b0-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="244b0-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="244b0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="244b0-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="244b0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="244b0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="244b0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="244b0-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="244b0-113">The call timed out.</span></span>|  
|<span data-ttu-id="244b0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="244b0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="244b0-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="244b0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="244b0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="244b0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="244b0-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="244b0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="244b0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="244b0-118">E_FAIL</span></span>|<span data-ttu-id="244b0-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="244b0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="244b0-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="244b0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="244b0-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="244b0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="244b0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="244b0-122">Remarks</span></span>  
 <span data-ttu-id="244b0-123">Среда CLR вызывает `SuspensionStarting` для информирования основного, возникающей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="244b0-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="244b0-124">Не следует перепланировать этой задачи.</span><span class="sxs-lookup"><span data-stu-id="244b0-124">Do not reschedule this task.</span></span> <span data-ttu-id="244b0-125">Узел должен запланировать повторное выполнение задачи при [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) вызывается.</span><span class="sxs-lookup"><span data-stu-id="244b0-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="244b0-126">Требования</span><span class="sxs-lookup"><span data-stu-id="244b0-126">Requirements</span></span>  
 <span data-ttu-id="244b0-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="244b0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="244b0-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="244b0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="244b0-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="244b0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="244b0-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="244b0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244b0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="244b0-131">See also</span></span>

- [<span data-ttu-id="244b0-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="244b0-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="244b0-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="244b0-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="244b0-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="244b0-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="244b0-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="244b0-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="244b0-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="244b0-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
