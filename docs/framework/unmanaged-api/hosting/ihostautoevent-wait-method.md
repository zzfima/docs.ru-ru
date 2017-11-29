---
title: "Метод IHostAutoEvent::Wait"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a4900d1edc69ad00c98455d388714c2fd1a5156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="006d0-102">Метод IHostAutoEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="006d0-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="006d0-103">Вызывает текущий [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр ожидать его признания или определенного времени.</span><span class="sxs-lookup"><span data-stu-id="006d0-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="006d0-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="006d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="006d0-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="006d0-106">[in] Количество миллисекунд текущего `IHostAutoEvent` экземпляр будет ожидать перед возвратом, если ни один поток или волокон принимает право на владение.</span><span class="sxs-lookup"><span data-stu-id="006d0-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="006d0-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, определяющее действие должен предпринять узел при этом операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="006d0-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="006d0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="006d0-108">Return Value</span></span>  
  
|<span data-ttu-id="006d0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="006d0-109">HRESULT</span></span>|<span data-ttu-id="006d0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="006d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="006d0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="006d0-111">S_OK</span></span>|<span data-ttu-id="006d0-112">`Wait`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="006d0-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="006d0-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="006d0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="006d0-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="006d0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="006d0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="006d0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="006d0-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="006d0-116">The call timed out.</span></span>|  
|<span data-ttu-id="006d0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="006d0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="006d0-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="006d0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="006d0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="006d0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="006d0-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="006d0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="006d0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="006d0-121">E_FAIL</span></span>|<span data-ttu-id="006d0-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="006d0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="006d0-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="006d0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="006d0-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="006d0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="006d0-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="006d0-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="006d0-126">Узел обнаружил взаимоблокировку в период ожидания при выборе события, представленного текущим `IHostAutoEvent` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="006d0-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="006d0-127">Требования</span><span class="sxs-lookup"><span data-stu-id="006d0-127">Requirements</span></span>  
 <span data-ttu-id="006d0-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="006d0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="006d0-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="006d0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="006d0-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="006d0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="006d0-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="006d0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006d0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="006d0-132">See Also</span></span>  
 [<span data-ttu-id="006d0-133">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="006d0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="006d0-134">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="006d0-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="006d0-135">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="006d0-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="006d0-136">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="006d0-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
