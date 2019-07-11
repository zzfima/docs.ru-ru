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
ms.openlocfilehash: b50e08e6fe0db7d16c87d9acccf77e2b15094039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749635"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="0df93-102">Метод IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="0df93-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="0df93-103">Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы, после предыдущего вызова [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="0df93-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0df93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0df93-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0df93-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0df93-105">Return Value</span></span>  
  
|<span data-ttu-id="0df93-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0df93-106">HRESULT</span></span>|<span data-ttu-id="0df93-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0df93-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0df93-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0df93-108">S_OK</span></span>|<span data-ttu-id="0df93-109">`EndThreadAffinity` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0df93-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="0df93-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0df93-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0df93-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0df93-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0df93-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0df93-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0df93-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0df93-113">The call timed out.</span></span>|  
|<span data-ttu-id="0df93-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0df93-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0df93-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0df93-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0df93-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0df93-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0df93-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0df93-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0df93-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0df93-118">E_FAIL</span></span>|<span data-ttu-id="0df93-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0df93-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0df93-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0df93-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0df93-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0df93-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0df93-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="0df93-122">E_UNEXPECTED</span></span>|<span data-ttu-id="0df93-123">`EndThreadAffinity` был вызван без ранее соответствующего вызова `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="0df93-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0df93-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0df93-124">Remarks</span></span>  
 <span data-ttu-id="0df93-125">Среда CLR не дает соответствующего вызова `BeginThreadAffinity` для текущей задачи перед вызовом `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="0df93-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="0df93-126">При отсутствии такого соответствующего вызова от реализации узлом [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) следует возвращают E_UNEXPECTED, а не выполнять никаких действий.</span><span class="sxs-lookup"><span data-stu-id="0df93-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0df93-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0df93-127">Requirements</span></span>  
 <span data-ttu-id="0df93-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0df93-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0df93-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0df93-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0df93-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0df93-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0df93-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0df93-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df93-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0df93-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="0df93-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0df93-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0df93-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0df93-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0df93-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="0df93-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0df93-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0df93-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
