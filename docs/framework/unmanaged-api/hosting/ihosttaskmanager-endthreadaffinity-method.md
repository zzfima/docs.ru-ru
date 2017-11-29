---
title: "Метод IHostTaskManager::EndThreadAffinity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EndThreadAffinity
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3b1c67397408253a11a12263ea9c9b45429a133
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="8d993-102">Метод IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="8d993-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="8d993-103">Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы после предыдущего вызова для [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="8d993-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d993-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d993-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8d993-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8d993-105">Return Value</span></span>  
  
|<span data-ttu-id="8d993-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d993-106">HRESULT</span></span>|<span data-ttu-id="8d993-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8d993-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d993-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d993-108">S_OK</span></span>|<span data-ttu-id="8d993-109">`EndThreadAffinity`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8d993-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="8d993-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d993-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d993-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8d993-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d993-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d993-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d993-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="8d993-113">The call timed out.</span></span>|  
|<span data-ttu-id="8d993-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d993-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d993-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="8d993-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d993-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d993-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d993-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="8d993-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d993-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d993-118">E_FAIL</span></span>|<span data-ttu-id="8d993-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8d993-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d993-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8d993-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d993-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8d993-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8d993-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="8d993-122">E_UNEXPECTED</span></span>|<span data-ttu-id="8d993-123">`EndThreadAffinity`был вызван без ранее соответствующего вызова `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="8d993-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d993-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d993-124">Remarks</span></span>  
 <span data-ttu-id="8d993-125">Среда CLR вызывает соответствующий метод `BeginThreadAffinity` для текущей задачи перед вызовом `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="8d993-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="8d993-126">При отсутствии такого соответствующего вызова реализация [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должен возвратить значение E_UNEXPECTED и не выполнять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="8d993-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d993-127">Требования</span><span class="sxs-lookup"><span data-stu-id="8d993-127">Requirements</span></span>  
 <span data-ttu-id="8d993-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d993-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d993-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d993-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d993-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d993-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d993-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d993-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d993-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8d993-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="8d993-133">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d993-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8d993-134">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d993-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8d993-135">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d993-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8d993-136">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8d993-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
