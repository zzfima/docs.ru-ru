---
title: "Метод IHostManualEvent::Reset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1bbd10437662fc8b7fbb52d65d196d7a519538b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="c54e1-102">Метод IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="c54e1-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="c54e1-103">Сбрасывает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) несигнальное состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c54e1-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c54e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c54e1-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c54e1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c54e1-105">Return Value</span></span>  
  
|<span data-ttu-id="c54e1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c54e1-106">HRESULT</span></span>|<span data-ttu-id="c54e1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c54e1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c54e1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c54e1-108">S_OK</span></span>|<span data-ttu-id="c54e1-109">`Reset`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c54e1-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="c54e1-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c54e1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c54e1-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c54e1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c54e1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c54e1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c54e1-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c54e1-113">The call timed out.</span></span>|  
|<span data-ttu-id="c54e1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c54e1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c54e1-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c54e1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c54e1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c54e1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c54e1-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c54e1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c54e1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c54e1-118">E_FAIL</span></span>|<span data-ttu-id="c54e1-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c54e1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c54e1-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c54e1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c54e1-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c54e1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c54e1-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c54e1-122">Requirements</span></span>  
 <span data-ttu-id="c54e1-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c54e1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c54e1-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c54e1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c54e1-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c54e1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c54e1-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c54e1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c54e1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c54e1-127">See Also</span></span>  
 [<span data-ttu-id="c54e1-128">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c54e1-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c54e1-129">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="c54e1-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="c54e1-130">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="c54e1-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="c54e1-131">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="c54e1-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="c54e1-132">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c54e1-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
