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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbce5e61f2013513d2079b5a958270319d34857
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763756"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="0ae2f-102">Метод IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="0ae2f-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="0ae2f-103">Задает счетчик прокруток для текущего [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ae2f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ae2f-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="0ae2f-106">[in] Новый счетчик прокруток для текущего `IHostCrst` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ae2f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0ae2f-107">Return Value</span></span>  
  
|<span data-ttu-id="0ae2f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ae2f-108">HRESULT</span></span>|<span data-ttu-id="0ae2f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0ae2f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ae2f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ae2f-110">S_OK</span></span>|<span data-ttu-id="0ae2f-111">`SetSpinCount` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="0ae2f-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ae2f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ae2f-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ae2f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ae2f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ae2f-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ae2f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ae2f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ae2f-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ae2f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ae2f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ae2f-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ae2f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ae2f-120">E_FAIL</span></span>|<span data-ttu-id="0ae2f-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ae2f-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ae2f-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ae2f-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ae2f-124">Remarks</span></span>  
 <span data-ttu-id="0ae2f-125">В многопроцессорных системах, если критический раздел, представленный текущим `IHostCrst` экземпляр недоступен, вызывающий поток выполняет `dwSpinCount` раз перед вызовом [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) для семафора, связанного с помощью критический раздел.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="0ae2f-126">Если во время операции управления "Счетчик" критический раздел стал доступным, вызывающий поток позволяет избежать операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="0ae2f-127">Использование `dwSpinCount` идентична использования параметра с тем же именем в Win32 `InitializeCriticalSectionAndSpinCount` функции.</span><span class="sxs-lookup"><span data-stu-id="0ae2f-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae2f-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0ae2f-128">Requirements</span></span>  
 <span data-ttu-id="0ae2f-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae2f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae2f-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ae2f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ae2f-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ae2f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ae2f-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae2f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae2f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0ae2f-133">See also</span></span>

- [<span data-ttu-id="0ae2f-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0ae2f-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0ae2f-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="0ae2f-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="0ae2f-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0ae2f-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
