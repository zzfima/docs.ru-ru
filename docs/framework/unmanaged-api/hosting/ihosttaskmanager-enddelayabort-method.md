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
ms.openlocfilehash: d3e8691461179e4f70a4617fd9487949df62f6cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444383"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="38e08-102">Метод IHostTaskManager::EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="38e08-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="38e08-103">Уведомляет хост, что управляемый код завершается из-за период, в котором текущей задачи недопустимо, после любого вызова для [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="38e08-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e08-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="38e08-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="38e08-105">Return Value</span></span>  
  
|<span data-ttu-id="38e08-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38e08-106">HRESULT</span></span>|<span data-ttu-id="38e08-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38e08-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38e08-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="38e08-108">S_OK</span></span>|<span data-ttu-id="38e08-109">`EndDelayAbort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="38e08-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="38e08-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="38e08-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="38e08-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="38e08-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="38e08-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="38e08-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="38e08-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="38e08-113">The call timed out.</span></span>|  
|<span data-ttu-id="38e08-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="38e08-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="38e08-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="38e08-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="38e08-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="38e08-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="38e08-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="38e08-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="38e08-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="38e08-118">E_FAIL</span></span>|<span data-ttu-id="38e08-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="38e08-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="38e08-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="38e08-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="38e08-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="38e08-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="38e08-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="38e08-122">E_UNEXPECTED</span></span>|<span data-ttu-id="38e08-123">`EndDelayAbort` был вызван без соответствующего вызова `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="38e08-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38e08-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="38e08-124">Remarks</span></span>  
 <span data-ttu-id="38e08-125">Среда CLR вызывает соответствующий метод `BeginDelayAbort` для текущей задачи перед вызовом `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="38e08-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="38e08-126">При отсутствии такого соответствующего вызова реализация [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должен возвращать E_UNEXPECTED из `EndDelayAbort`и не предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="38e08-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e08-127">Требования</span><span class="sxs-lookup"><span data-stu-id="38e08-127">Requirements</span></span>  
 <span data-ttu-id="38e08-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e08-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e08-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38e08-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38e08-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38e08-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38e08-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e08-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e08-132">См. также</span><span class="sxs-lookup"><span data-stu-id="38e08-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="38e08-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="38e08-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="38e08-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="38e08-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="38e08-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="38e08-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="38e08-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="38e08-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
