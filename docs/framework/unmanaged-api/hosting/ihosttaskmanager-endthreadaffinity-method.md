---
title: Метод IHostTaskManager::EndThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb07e38542893b26595b67d6cf0fa77c522b4def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="46856-102">Метод IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="46856-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="46856-103">Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы после предыдущего вызова для [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="46856-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46856-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46856-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="46856-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46856-105">Return Value</span></span>  
  
|<span data-ttu-id="46856-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46856-106">HRESULT</span></span>|<span data-ttu-id="46856-107">Описание</span><span class="sxs-lookup"><span data-stu-id="46856-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46856-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="46856-108">S_OK</span></span>|<span data-ttu-id="46856-109">`EndThreadAffinity` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="46856-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="46856-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46856-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46856-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="46856-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46856-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46856-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46856-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="46856-113">The call timed out.</span></span>|  
|<span data-ttu-id="46856-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46856-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46856-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="46856-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46856-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46856-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46856-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="46856-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46856-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46856-118">E_FAIL</span></span>|<span data-ttu-id="46856-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="46856-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46856-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="46856-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46856-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="46856-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="46856-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="46856-122">E_UNEXPECTED</span></span>|<span data-ttu-id="46856-123">`EndThreadAffinity` был вызван без ранее соответствующего вызова `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="46856-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46856-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="46856-124">Remarks</span></span>  
 <span data-ttu-id="46856-125">Среда CLR вызывает соответствующий метод `BeginThreadAffinity` для текущей задачи перед вызовом `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="46856-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="46856-126">При отсутствии такого соответствующего вызова реализация [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должен возвратить значение E_UNEXPECTED и не выполнять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="46856-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46856-127">Требования</span><span class="sxs-lookup"><span data-stu-id="46856-127">Requirements</span></span>  
 <span data-ttu-id="46856-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46856-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46856-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46856-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46856-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46856-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46856-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46856-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46856-132">См. также</span><span class="sxs-lookup"><span data-stu-id="46856-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="46856-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="46856-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="46856-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="46856-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="46856-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="46856-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="46856-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="46856-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
