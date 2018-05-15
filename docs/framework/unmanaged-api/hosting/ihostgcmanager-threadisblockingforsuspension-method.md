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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85921156860f52eb2a898e6be356e191c2a4f02d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="3ca8f-102">Метод IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="3ca8f-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="3ca8f-103">Уведомляет хост, что поток, из которого был выполнен вызов метода готов заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ca8f-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3ca8f-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3ca8f-105">Return Value</span></span>  
  
|<span data-ttu-id="3ca8f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ca8f-106">HRESULT</span></span>|<span data-ttu-id="3ca8f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3ca8f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ca8f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ca8f-108">S_OK</span></span>|<span data-ttu-id="3ca8f-109">`ThreadIsBlockingForSuspension` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="3ca8f-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ca8f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ca8f-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ca8f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ca8f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ca8f-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-113">The call timed out.</span></span>|  
|<span data-ttu-id="3ca8f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ca8f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ca8f-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ca8f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ca8f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ca8f-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ca8f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ca8f-118">E_FAIL</span></span>|<span data-ttu-id="3ca8f-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ca8f-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ca8f-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca8f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ca8f-122">Remarks</span></span>  
 <span data-ttu-id="3ca8f-123">Как правило, среда CLR вызывает `ThreadIsBlockForSuspension` метод в процессе подготовки для сборки мусора, чтобы предоставить возможность повторного планирования потока для неуправляемых задач узла.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ca8f-124">Узел можно запланировать повторное выполнение задачи только после вызова `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="3ca8f-125">После выполнения вызовов [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), основное приложение не должно планировать задачу.</span><span class="sxs-lookup"><span data-stu-id="3ca8f-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca8f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="3ca8f-126">Requirements</span></span>  
 <span data-ttu-id="3ca8f-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca8f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca8f-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3ca8f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ca8f-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ca8f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ca8f-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca8f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca8f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3ca8f-131">See Also</span></span>  
 [<span data-ttu-id="3ca8f-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3ca8f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3ca8f-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3ca8f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3ca8f-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="3ca8f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3ca8f-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3ca8f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3ca8f-136">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="3ca8f-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
