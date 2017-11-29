---
title: "Метод IHostGCManager::ThreadIsBlockingForSuspension"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ea5f110754b8b607673bcbd4060dee85cd5ca9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="d2da1-102">Метод IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="d2da1-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="d2da1-103">Уведомляет хост, что поток, из которого был выполнен вызов метода готов заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="d2da1-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2da1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2da1-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d2da1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d2da1-105">Return Value</span></span>  
  
|<span data-ttu-id="d2da1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2da1-106">HRESULT</span></span>|<span data-ttu-id="d2da1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d2da1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2da1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2da1-108">S_OK</span></span>|<span data-ttu-id="d2da1-109">`ThreadIsBlockingForSuspension`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d2da1-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="d2da1-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d2da1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d2da1-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d2da1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d2da1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d2da1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d2da1-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d2da1-113">The call timed out.</span></span>|  
|<span data-ttu-id="d2da1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d2da1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d2da1-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d2da1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d2da1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d2da1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d2da1-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d2da1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d2da1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d2da1-118">E_FAIL</span></span>|<span data-ttu-id="d2da1-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d2da1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d2da1-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d2da1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d2da1-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d2da1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2da1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2da1-122">Remarks</span></span>  
 <span data-ttu-id="d2da1-123">Как правило, среда CLR вызывает `ThreadIsBlockForSuspension` метод в процессе подготовки для сборки мусора, чтобы предоставить возможность повторного планирования потока для неуправляемых задач узла.</span><span class="sxs-lookup"><span data-stu-id="d2da1-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2da1-124">Узел можно запланировать повторное выполнение задачи только после вызова `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="d2da1-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="d2da1-125">После выполнения вызовов [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), основное приложение не должно планировать задачу.</span><span class="sxs-lookup"><span data-stu-id="d2da1-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2da1-126">Требования</span><span class="sxs-lookup"><span data-stu-id="d2da1-126">Requirements</span></span>  
 <span data-ttu-id="d2da1-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2da1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2da1-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2da1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2da1-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2da1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2da1-130">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2da1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2da1-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d2da1-131">See Also</span></span>  
 [<span data-ttu-id="d2da1-132">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2da1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d2da1-133">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2da1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d2da1-134">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2da1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d2da1-135">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2da1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="d2da1-136">IHostGCManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2da1-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
