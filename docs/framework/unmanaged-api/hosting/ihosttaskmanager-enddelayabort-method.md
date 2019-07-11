---
title: Метод IHostTaskManager::EndDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95446996988a22e0d4495f3e0da9f6d2432f5a7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749716"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="85e69-102">Метод IHostTaskManager::EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="85e69-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="85e69-103">Уведомляет хост, что управляемый код завершает работу период, в котором текущей задачи недопустимо, после предыдущего вызова [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="85e69-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85e69-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="85e69-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85e69-105">Return Value</span></span>  
  
|<span data-ttu-id="85e69-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85e69-106">HRESULT</span></span>|<span data-ttu-id="85e69-107">Описание</span><span class="sxs-lookup"><span data-stu-id="85e69-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85e69-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="85e69-108">S_OK</span></span>|<span data-ttu-id="85e69-109">`EndDelayAbort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="85e69-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="85e69-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85e69-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85e69-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="85e69-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85e69-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85e69-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85e69-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="85e69-113">The call timed out.</span></span>|  
|<span data-ttu-id="85e69-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85e69-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85e69-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="85e69-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85e69-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85e69-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85e69-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="85e69-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85e69-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85e69-118">E_FAIL</span></span>|<span data-ttu-id="85e69-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="85e69-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85e69-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="85e69-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85e69-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85e69-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="85e69-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="85e69-122">E_UNEXPECTED</span></span>|<span data-ttu-id="85e69-123">`EndDelayAbort` был вызван без соответствующего вызова `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="85e69-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85e69-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="85e69-124">Remarks</span></span>  
 <span data-ttu-id="85e69-125">Среда CLR не дает соответствующего вызова `BeginDelayAbort` для текущей задачи перед вызовом `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="85e69-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="85e69-126">При отсутствии такого соответствующего вызова от реализации узлом [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должен возвращать E_UNEXPECTED из `EndDelayAbort`и не предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="85e69-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e69-127">Требования</span><span class="sxs-lookup"><span data-stu-id="85e69-127">Requirements</span></span>  
 <span data-ttu-id="85e69-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85e69-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e69-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85e69-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85e69-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85e69-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85e69-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e69-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e69-132">См. также</span><span class="sxs-lookup"><span data-stu-id="85e69-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="85e69-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="85e69-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="85e69-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="85e69-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="85e69-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="85e69-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="85e69-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="85e69-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
