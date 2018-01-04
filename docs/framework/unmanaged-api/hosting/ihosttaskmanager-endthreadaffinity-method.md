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
ms.workload: dotnet
ms.openlocfilehash: b12bdc16d70b9e4ccaecbee1b8bcd4e8f05d59dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="31f51-102">Метод IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="31f51-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="31f51-103">Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы после предыдущего вызова для [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="31f51-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31f51-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="31f51-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31f51-105">Return Value</span></span>  
  
|<span data-ttu-id="31f51-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31f51-106">HRESULT</span></span>|<span data-ttu-id="31f51-107">Описание</span><span class="sxs-lookup"><span data-stu-id="31f51-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31f51-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="31f51-108">S_OK</span></span>|<span data-ttu-id="31f51-109">`EndThreadAffinity`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="31f51-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="31f51-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31f51-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31f51-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="31f51-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31f51-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31f51-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31f51-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="31f51-113">The call timed out.</span></span>|  
|<span data-ttu-id="31f51-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31f51-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31f51-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="31f51-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31f51-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31f51-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31f51-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="31f51-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31f51-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31f51-118">E_FAIL</span></span>|<span data-ttu-id="31f51-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="31f51-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31f51-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="31f51-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31f51-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="31f51-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="31f51-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="31f51-122">E_UNEXPECTED</span></span>|<span data-ttu-id="31f51-123">`EndThreadAffinity`был вызван без ранее соответствующего вызова `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="31f51-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31f51-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="31f51-124">Remarks</span></span>  
 <span data-ttu-id="31f51-125">Среда CLR вызывает соответствующий метод `BeginThreadAffinity` для текущей задачи перед вызовом `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="31f51-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="31f51-126">При отсутствии такого соответствующего вызова реализация [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должен возвратить значение E_UNEXPECTED и не выполнять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="31f51-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f51-127">Требования</span><span class="sxs-lookup"><span data-stu-id="31f51-127">Requirements</span></span>  
 <span data-ttu-id="31f51-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f51-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f51-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="31f51-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31f51-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31f51-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31f51-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f51-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f51-132">См. также</span><span class="sxs-lookup"><span data-stu-id="31f51-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="31f51-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="31f51-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="31f51-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="31f51-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="31f51-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="31f51-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="31f51-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="31f51-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
