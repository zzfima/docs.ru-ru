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
ms.openlocfilehash: cf79c0d0f6def46d7f4d55f17afbd1f1dff00ad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133076"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="299bb-102">Метод IHostTaskManager::EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="299bb-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="299bb-103">Уведомляет узел о выходе управляемого кода за время, в течение которого текущая задача не должна прерываться, после предыдущего вызова [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="299bb-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="299bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="299bb-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="299bb-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="299bb-105">Return Value</span></span>  
  
|<span data-ttu-id="299bb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="299bb-106">HRESULT</span></span>|<span data-ttu-id="299bb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="299bb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="299bb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="299bb-108">S_OK</span></span>|<span data-ttu-id="299bb-109">`EndDelayAbort` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="299bb-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="299bb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="299bb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="299bb-111">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="299bb-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="299bb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="299bb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="299bb-113">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="299bb-113">The call timed out.</span></span>|  
|<span data-ttu-id="299bb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="299bb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="299bb-115">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="299bb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="299bb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="299bb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="299bb-117">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="299bb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="299bb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="299bb-118">E_FAIL</span></span>|<span data-ttu-id="299bb-119">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="299bb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="299bb-120">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="299bb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="299bb-121">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="299bb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="299bb-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="299bb-122">E_UNEXPECTED</span></span>|<span data-ttu-id="299bb-123">`EndDelayAbort` был вызван без соответствующего вызова `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="299bb-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="299bb-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="299bb-124">Remarks</span></span>  
 <span data-ttu-id="299bb-125">Среда CLR выполняет соответствующий вызов `BeginDelayAbort` в текущей задаче перед вызовом `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="299bb-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="299bb-126">В отсутствие такого соответствующего вызова реализация [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) должна возвращать E_UNEXPECTED из `EndDelayAbort`и не должна предпринимать никаких действий.</span><span class="sxs-lookup"><span data-stu-id="299bb-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="299bb-127">Требования</span><span class="sxs-lookup"><span data-stu-id="299bb-127">Requirements</span></span>  
 <span data-ttu-id="299bb-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="299bb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="299bb-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="299bb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="299bb-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="299bb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="299bb-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="299bb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299bb-132">См. также</span><span class="sxs-lookup"><span data-stu-id="299bb-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="299bb-133">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="299bb-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="299bb-134">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="299bb-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="299bb-135">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="299bb-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="299bb-136">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="299bb-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
