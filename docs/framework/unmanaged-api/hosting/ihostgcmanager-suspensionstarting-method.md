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
ms.openlocfilehash: e3e808c7ed03d7b4cc9dfe77389df6b2eff491f7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937712"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="602ca-102">Метод IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="602ca-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="602ca-103">Уведомляет основное приложение о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="602ca-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="602ca-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="602ca-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="602ca-105">Return Value</span></span>  
  
|<span data-ttu-id="602ca-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="602ca-106">HRESULT</span></span>|<span data-ttu-id="602ca-107">Описание</span><span class="sxs-lookup"><span data-stu-id="602ca-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="602ca-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="602ca-108">S_OK</span></span>|<span data-ttu-id="602ca-109">`SuspensionStarting`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="602ca-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="602ca-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="602ca-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="602ca-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="602ca-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="602ca-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="602ca-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="602ca-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="602ca-113">The call timed out.</span></span>|  
|<span data-ttu-id="602ca-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="602ca-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="602ca-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="602ca-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="602ca-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="602ca-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="602ca-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="602ca-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="602ca-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="602ca-118">E_FAIL</span></span>|<span data-ttu-id="602ca-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="602ca-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="602ca-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="602ca-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="602ca-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="602ca-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="602ca-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="602ca-122">Remarks</span></span>  
 <span data-ttu-id="602ca-123">Вызовы `SuspensionStarting` CLR для информирования узла о сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="602ca-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="602ca-124">Не Перепланируйте эту задачу.</span><span class="sxs-lookup"><span data-stu-id="602ca-124">Do not reschedule this task.</span></span> <span data-ttu-id="602ca-125">Узел должен перепланировать задачу при вызове [среадисблоккингфорсуспенсион](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="602ca-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="602ca-126">Требования</span><span class="sxs-lookup"><span data-stu-id="602ca-126">Requirements</span></span>  
 <span data-ttu-id="602ca-127">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602ca-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602ca-128">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="602ca-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="602ca-129">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="602ca-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="602ca-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602ca-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602ca-131">См. также</span><span class="sxs-lookup"><span data-stu-id="602ca-131">See also</span></span>

- [<span data-ttu-id="602ca-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="602ca-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="602ca-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="602ca-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="602ca-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="602ca-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="602ca-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="602ca-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="602ca-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="602ca-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
