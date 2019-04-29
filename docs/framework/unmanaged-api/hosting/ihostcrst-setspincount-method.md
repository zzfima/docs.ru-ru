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
ms.openlocfilehash: 3ca17a6814b56c0fe781cfb28a35a576f02f1943
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967691"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="d87fa-102">Метод IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="d87fa-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="d87fa-103">Задает счетчик прокруток для текущего [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d87fa-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d87fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d87fa-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d87fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d87fa-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="d87fa-106">[in] Новый счетчик прокруток для текущего `IHostCrst` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d87fa-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d87fa-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d87fa-107">Return Value</span></span>  
  
|<span data-ttu-id="d87fa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d87fa-108">HRESULT</span></span>|<span data-ttu-id="d87fa-109">Описание</span><span class="sxs-lookup"><span data-stu-id="d87fa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d87fa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d87fa-110">S_OK</span></span>|<span data-ttu-id="d87fa-111">`SetSpinCount` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d87fa-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="d87fa-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d87fa-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d87fa-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d87fa-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d87fa-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d87fa-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d87fa-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d87fa-115">The call timed out.</span></span>|  
|<span data-ttu-id="d87fa-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d87fa-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d87fa-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d87fa-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d87fa-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d87fa-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d87fa-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d87fa-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d87fa-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d87fa-120">E_FAIL</span></span>|<span data-ttu-id="d87fa-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="d87fa-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d87fa-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d87fa-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d87fa-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d87fa-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d87fa-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d87fa-124">Remarks</span></span>  
 <span data-ttu-id="d87fa-125">В многопроцессорных системах, если критический раздел, представленный текущим `IHostCrst` экземпляр недоступен, вызывающий поток выполняет `dwSpinCount` раз перед вызовом [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) для семафора, связанного с помощью критический раздел.</span><span class="sxs-lookup"><span data-stu-id="d87fa-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="d87fa-126">Если во время операции управления "Счетчик" критический раздел стал доступным, вызывающий поток позволяет избежать операцию ожидания.</span><span class="sxs-lookup"><span data-stu-id="d87fa-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="d87fa-127">Использование `dwSpinCount` идентична использования параметра с тем же именем в Win32 `InitializeCriticalSectionAndSpinCount` функции.</span><span class="sxs-lookup"><span data-stu-id="d87fa-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d87fa-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d87fa-128">Requirements</span></span>  
 <span data-ttu-id="d87fa-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d87fa-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d87fa-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d87fa-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d87fa-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d87fa-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d87fa-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d87fa-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87fa-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d87fa-133">See also</span></span>

- [<span data-ttu-id="d87fa-134">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d87fa-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d87fa-135">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="d87fa-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="d87fa-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d87fa-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
