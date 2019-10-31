---
title: Метод IHostCrst::SetSpinCount
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: a8642235cda359b849c49a35ab565397402c37d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130506"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="dae2e-102">Метод IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="dae2e-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="dae2e-103">Задает счетчик прокрутки для текущего экземпляра [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dae2e-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dae2e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dae2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dae2e-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="dae2e-106">окне Новое количество прокруток для текущего экземпляра `IHostCrst`.</span><span class="sxs-lookup"><span data-stu-id="dae2e-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dae2e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dae2e-107">Return Value</span></span>  
  
|<span data-ttu-id="dae2e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dae2e-108">HRESULT</span></span>|<span data-ttu-id="dae2e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="dae2e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dae2e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dae2e-110">S_OK</span></span>|<span data-ttu-id="dae2e-111">`SetSpinCount` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="dae2e-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="dae2e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dae2e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dae2e-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="dae2e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dae2e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dae2e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dae2e-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="dae2e-115">The call timed out.</span></span>|  
|<span data-ttu-id="dae2e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dae2e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dae2e-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="dae2e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dae2e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dae2e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dae2e-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="dae2e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dae2e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dae2e-120">E_FAIL</span></span>|<span data-ttu-id="dae2e-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="dae2e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dae2e-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="dae2e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dae2e-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dae2e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dae2e-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="dae2e-124">Remarks</span></span>  
 <span data-ttu-id="dae2e-125">В многопроцессорных системах, если критическая секция, представленная текущим экземпляром `IHostCrst`, недоступна, вызывающий поток вращает `dwSpinCount` раз перед вызовом [IHostSemaphore:: wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) для семафора, связанного с критическим разделом.</span><span class="sxs-lookup"><span data-stu-id="dae2e-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="dae2e-126">Если критическая секция будет свободна во время операции Spin, вызывающий поток не будет выполнять операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="dae2e-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="dae2e-127">Использование `dwSpinCount` идентично использованию параметра с тем же именем в функции `InitializeCriticalSectionAndSpinCount` Win32.</span><span class="sxs-lookup"><span data-stu-id="dae2e-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dae2e-128">Требования</span><span class="sxs-lookup"><span data-stu-id="dae2e-128">Requirements</span></span>  
 <span data-ttu-id="dae2e-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dae2e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dae2e-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dae2e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dae2e-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dae2e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dae2e-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dae2e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae2e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dae2e-133">See also</span></span>

- [<span data-ttu-id="dae2e-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="dae2e-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dae2e-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="dae2e-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="dae2e-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dae2e-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
