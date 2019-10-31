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
ms.openlocfilehash: bf1b830f55110c00356527bc9caa41dfd94ae377
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130459"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="c48a4-102">Метод IHostGCManager::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="c48a4-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="c48a4-103">Уведомляет основное приложение о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c48a4-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c48a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c48a4-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c48a4-105">Return Value</span></span>  
  
|<span data-ttu-id="c48a4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c48a4-106">HRESULT</span></span>|<span data-ttu-id="c48a4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c48a4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c48a4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c48a4-108">S_OK</span></span>|<span data-ttu-id="c48a4-109">`SuspensionStarting` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c48a4-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="c48a4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c48a4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c48a4-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c48a4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c48a4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c48a4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c48a4-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="c48a4-113">The call timed out.</span></span>|  
|<span data-ttu-id="c48a4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c48a4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c48a4-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c48a4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c48a4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c48a4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c48a4-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="c48a4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c48a4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c48a4-118">E_FAIL</span></span>|<span data-ttu-id="c48a4-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c48a4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c48a4-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c48a4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c48a4-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c48a4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c48a4-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="c48a4-122">Remarks</span></span>  
 <span data-ttu-id="c48a4-123">Среда CLR вызывает `SuspensionStarting`, чтобы сообщить узлу о возникновении сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c48a4-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c48a4-124">Не Перепланируйте эту задачу.</span><span class="sxs-lookup"><span data-stu-id="c48a4-124">Do not reschedule this task.</span></span> <span data-ttu-id="c48a4-125">Узел должен перепланировать задачу при вызове [среадисблоккингфорсуспенсион](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c48a4-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c48a4-126">Требования</span><span class="sxs-lookup"><span data-stu-id="c48a4-126">Requirements</span></span>  
 <span data-ttu-id="c48a4-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c48a4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48a4-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c48a4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c48a4-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c48a4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c48a4-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48a4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48a4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c48a4-131">See also</span></span>

- [<span data-ttu-id="c48a4-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c48a4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c48a4-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c48a4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c48a4-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="c48a4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c48a4-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c48a4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="c48a4-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="c48a4-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
