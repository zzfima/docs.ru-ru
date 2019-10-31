---
title: Метод IHostSemaphore::Wait
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: bf09f7bc6c3e3aabfc16f9cad277c46be024b01d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139453"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="2b651-102">Метод IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="2b651-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="2b651-103">Приводит к тому, что текущий экземпляр [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) ожидает его признания или истечения указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="2b651-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b651-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b651-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b651-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b651-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="2b651-106">окне Число миллисекунд ожидания перед возвратом, если текущий экземпляр `IHostSemaphore` не владеет.</span><span class="sxs-lookup"><span data-stu-id="2b651-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="2b651-107">окне Одно из значений [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , указывающее действие, которое должен предпринять узел, если эта операция блокируется.</span><span class="sxs-lookup"><span data-stu-id="2b651-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b651-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b651-108">Return Value</span></span>  
  
|<span data-ttu-id="2b651-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b651-109">HRESULT</span></span>|<span data-ttu-id="2b651-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2b651-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b651-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b651-111">S_OK</span></span>|<span data-ttu-id="2b651-112">`Wait` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="2b651-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="2b651-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b651-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b651-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2b651-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b651-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b651-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b651-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="2b651-116">The call timed out.</span></span>|  
|<span data-ttu-id="2b651-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b651-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b651-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="2b651-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b651-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b651-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b651-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="2b651-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b651-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b651-121">E_FAIL</span></span>|<span data-ttu-id="2b651-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b651-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b651-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2b651-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b651-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2b651-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2b651-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="2b651-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="2b651-126">Узел обнаружил взаимоблокировку в течение интервала ожидания и выбрал текущий экземпляр `IHostSemaphore` в качестве жертвы взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="2b651-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b651-127">Требования</span><span class="sxs-lookup"><span data-stu-id="2b651-127">Requirements</span></span>  
 <span data-ttu-id="2b651-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b651-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b651-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2b651-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b651-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2b651-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b651-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b651-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b651-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2b651-132">See also</span></span>

- [<span data-ttu-id="2b651-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2b651-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2b651-134">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="2b651-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="2b651-135">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="2b651-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="2b651-136">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="2b651-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="2b651-137">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2b651-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
