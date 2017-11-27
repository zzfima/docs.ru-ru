---
title: "Метод IHostCrst::SetSpinCount"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.SetSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19172c6d498e5066c102c642105d78d10b26212c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="2f21b-102">Метод IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="2f21b-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="2f21b-103">Задает счетчик прокруток для текущего [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2f21b-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f21b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f21b-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f21b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f21b-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="2f21b-106">[in] Новый счетчик прокруток для текущего `IHostCrst` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2f21b-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f21b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f21b-107">Return Value</span></span>  
  
|<span data-ttu-id="2f21b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f21b-108">HRESULT</span></span>|<span data-ttu-id="2f21b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2f21b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f21b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f21b-110">S_OK</span></span>|<span data-ttu-id="2f21b-111">`SetSpinCount`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2f21b-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="2f21b-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f21b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f21b-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2f21b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f21b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f21b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f21b-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2f21b-115">The call timed out.</span></span>|  
|<span data-ttu-id="2f21b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f21b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f21b-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2f21b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f21b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f21b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f21b-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2f21b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f21b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f21b-120">E_FAIL</span></span>|<span data-ttu-id="2f21b-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="2f21b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f21b-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f21b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f21b-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f21b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f21b-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f21b-124">Remarks</span></span>  
 <span data-ttu-id="2f21b-125">В многопроцессорных системах, если критический раздел, представленный текущим `IHostCrst` экземпляр недоступен, вызывающий поток выполняет `dwSpinCount` раз перед вызовом метода [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) семафора связанные с критической секции.</span><span class="sxs-lookup"><span data-stu-id="2f21b-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="2f21b-126">Если критическая секция освобождается во время операции прокрутки, вызывающий поток позволяет избежать ожидания операции.</span><span class="sxs-lookup"><span data-stu-id="2f21b-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="2f21b-127">Использование `dwSpinCount` идентична использование параметра с тем же именем в Win32 `InitializeCriticalSectionAndSpinCount` функции.</span><span class="sxs-lookup"><span data-stu-id="2f21b-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f21b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="2f21b-128">Requirements</span></span>  
 <span data-ttu-id="2f21b-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f21b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f21b-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f21b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f21b-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f21b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f21b-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f21b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f21b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2f21b-133">See Also</span></span>  
 [<span data-ttu-id="2f21b-134">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2f21b-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="2f21b-135">IHostCrst-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2f21b-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="2f21b-136">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2f21b-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
