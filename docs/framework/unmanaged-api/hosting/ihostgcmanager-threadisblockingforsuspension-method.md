---
title: Метод IHostGCManager::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: cb807a6a344c49baeedfa88aef989a9cb2ec8a46
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133920"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="4d25d-102">Метод IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="4d25d-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="4d25d-103">Уведомляет узел о том, что поток, из которого был сделан вызов метода, собирается блокироваться для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4d25d-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d25d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d25d-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4d25d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4d25d-105">Return Value</span></span>  
  
|<span data-ttu-id="4d25d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d25d-106">HRESULT</span></span>|<span data-ttu-id="4d25d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4d25d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d25d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d25d-108">S_OK</span></span>|<span data-ttu-id="4d25d-109">`ThreadIsBlockingForSuspension` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="4d25d-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="4d25d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d25d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d25d-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4d25d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d25d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d25d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d25d-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="4d25d-113">The call timed out.</span></span>|  
|<span data-ttu-id="4d25d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d25d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d25d-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="4d25d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d25d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d25d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d25d-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="4d25d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d25d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d25d-118">E_FAIL</span></span>|<span data-ttu-id="4d25d-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4d25d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d25d-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4d25d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d25d-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d25d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d25d-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="4d25d-122">Remarks</span></span>  
 <span data-ttu-id="4d25d-123">Среда CLR обычно вызывает метод `ThreadIsBlockForSuspension` при подготовке к сборке мусора, чтобы дать узлу возможность перепланировать поток для неуправляемых задач.</span><span class="sxs-lookup"><span data-stu-id="4d25d-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4d25d-124">Узел может перепланировать задачи только после вызова `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="4d25d-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="4d25d-125">После того как среда выполнения вызовет [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), узел не должен перепланировать задачу.</span><span class="sxs-lookup"><span data-stu-id="4d25d-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d25d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="4d25d-126">Requirements</span></span>  
 <span data-ttu-id="4d25d-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d25d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d25d-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4d25d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d25d-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d25d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d25d-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d25d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d25d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="4d25d-131">See also</span></span>

- [<span data-ttu-id="4d25d-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4d25d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4d25d-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4d25d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4d25d-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4d25d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4d25d-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4d25d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="4d25d-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="4d25d-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
