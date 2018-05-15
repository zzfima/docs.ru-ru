---
title: Метод IHostAutoEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7921f0361d7369cddf14dd1ab477529d1bbac481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="74112-102">Метод IHostAutoEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="74112-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="74112-103">Вызывает текущий [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) экземпляр ожидать его признания или определенного времени.</span><span class="sxs-lookup"><span data-stu-id="74112-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74112-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74112-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74112-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74112-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="74112-106">[in] Количество миллисекунд текущего `IHostAutoEvent` экземпляр будет ожидать перед возвратом, если ни один поток или волокон принимает право на владение.</span><span class="sxs-lookup"><span data-stu-id="74112-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="74112-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, определяющее действие должен предпринять узел при этом операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="74112-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74112-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="74112-108">Return Value</span></span>  
  
|<span data-ttu-id="74112-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74112-109">HRESULT</span></span>|<span data-ttu-id="74112-110">Описание</span><span class="sxs-lookup"><span data-stu-id="74112-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74112-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74112-111">S_OK</span></span>|<span data-ttu-id="74112-112">`Wait` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="74112-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="74112-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74112-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74112-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="74112-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74112-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74112-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74112-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="74112-116">The call timed out.</span></span>|  
|<span data-ttu-id="74112-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74112-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74112-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="74112-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74112-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74112-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74112-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="74112-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74112-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74112-121">E_FAIL</span></span>|<span data-ttu-id="74112-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="74112-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74112-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="74112-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74112-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="74112-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74112-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="74112-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="74112-126">Узел обнаружил взаимоблокировку в период ожидания при выборе события, представленного текущим `IHostAutoEvent` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="74112-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74112-127">Требования</span><span class="sxs-lookup"><span data-stu-id="74112-127">Requirements</span></span>  
 <span data-ttu-id="74112-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74112-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74112-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74112-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74112-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74112-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74112-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74112-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74112-132">См. также</span><span class="sxs-lookup"><span data-stu-id="74112-132">See Also</span></span>  
 [<span data-ttu-id="74112-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="74112-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="74112-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="74112-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="74112-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="74112-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="74112-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="74112-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
