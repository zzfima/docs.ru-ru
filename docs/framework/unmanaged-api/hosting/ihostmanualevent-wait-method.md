---
title: "Метод IHostManualEvent::Wait"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2bd584e1ada69adca7f8ef77f98533ef7a1ba16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="5f512-102">Метод IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="5f512-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="5f512-103">Вызывает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляр ожидать его признания или определенного времени.</span><span class="sxs-lookup"><span data-stu-id="5f512-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f512-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f512-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f512-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f512-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="5f512-106">[in] Количество миллисекунд для ожидания перед возвратом, если текущий `IHostManualEvent` не является владельцем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5f512-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="5f512-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значения, указывающие действие должен предпринять узел при этом операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="5f512-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f512-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5f512-108">Return Value</span></span>  
  
|<span data-ttu-id="5f512-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f512-109">HRESULT</span></span>|<span data-ttu-id="5f512-110">Описание</span><span class="sxs-lookup"><span data-stu-id="5f512-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f512-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f512-111">S_OK</span></span>|<span data-ttu-id="5f512-112">`Wait`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5f512-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="5f512-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f512-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f512-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5f512-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f512-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f512-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f512-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5f512-116">The call timed out.</span></span>|  
|<span data-ttu-id="5f512-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f512-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f512-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5f512-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f512-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f512-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f512-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5f512-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f512-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f512-121">E_FAIL</span></span>|<span data-ttu-id="5f512-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="5f512-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f512-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5f512-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f512-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5f512-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5f512-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="5f512-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="5f512-126">Узел обнаружил взаимоблокировку в период ожидания при выборе текущего `IHostManualEvent` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="5f512-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f512-127">Требования</span><span class="sxs-lookup"><span data-stu-id="5f512-127">Requirements</span></span>  
 <span data-ttu-id="5f512-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f512-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f512-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f512-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f512-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f512-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f512-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f512-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f512-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5f512-132">See Also</span></span>  
 [<span data-ttu-id="5f512-133">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f512-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5f512-134">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f512-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="5f512-135">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f512-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="5f512-136">IHostSemaphore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f512-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="5f512-137">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f512-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
