---
title: Метод IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a70d5daf6626a26842d91ff6a35d0abf26d79ad1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492573"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="47607-102">Метод IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="47607-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="47607-103">Вызывает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляр ждать, пока он принадлежал или определенный промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="47607-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47607-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47607-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47607-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47607-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="47607-106">[in] Количество миллисекунд ожидания перед возвратом, если текущий `IHostManualEvent` экземпляр не принадлежит.</span><span class="sxs-lookup"><span data-stu-id="47607-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="47607-107">[in] Один из [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) значений, указывающий действие, выполняемое узлом, если это операция блокирует.</span><span class="sxs-lookup"><span data-stu-id="47607-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47607-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47607-108">Return Value</span></span>  
  
|<span data-ttu-id="47607-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47607-109">HRESULT</span></span>|<span data-ttu-id="47607-110">Описание</span><span class="sxs-lookup"><span data-stu-id="47607-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47607-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="47607-111">S_OK</span></span>|<span data-ttu-id="47607-112">`Wait` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="47607-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="47607-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47607-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47607-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="47607-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47607-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47607-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47607-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="47607-116">The call timed out.</span></span>|  
|<span data-ttu-id="47607-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47607-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47607-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="47607-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47607-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47607-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47607-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="47607-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47607-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47607-121">E_FAIL</span></span>|<span data-ttu-id="47607-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="47607-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47607-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="47607-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47607-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="47607-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="47607-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="47607-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="47607-126">Узел обнаружил взаимоблокировку в период ожидания и выберите текущий `IHostManualEvent` экземпляр в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="47607-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47607-127">Требования</span><span class="sxs-lookup"><span data-stu-id="47607-127">Requirements</span></span>  
 <span data-ttu-id="47607-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47607-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47607-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="47607-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47607-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47607-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47607-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47607-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47607-132">См. также</span><span class="sxs-lookup"><span data-stu-id="47607-132">See also</span></span>
- [<span data-ttu-id="47607-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="47607-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="47607-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="47607-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="47607-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="47607-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="47607-136">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="47607-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="47607-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="47607-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
