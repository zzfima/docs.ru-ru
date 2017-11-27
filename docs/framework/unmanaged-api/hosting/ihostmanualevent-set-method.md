---
title: "Метод IHostManualEvent::Set"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f093e1278e74553ed78445e0cb83127a219e622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="e78e7-102">Метод IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="e78e7-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="e78e7-103">Задает текущий [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="e78e7-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e78e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e78e7-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e78e7-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e78e7-105">Return Value</span></span>  
  
|<span data-ttu-id="e78e7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e78e7-106">HRESULT</span></span>|<span data-ttu-id="e78e7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e78e7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e78e7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e78e7-108">S_OK</span></span>|<span data-ttu-id="e78e7-109">`Set`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e78e7-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="e78e7-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e78e7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e78e7-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e78e7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e78e7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e78e7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e78e7-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e78e7-113">The call timed out.</span></span>|  
|<span data-ttu-id="e78e7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e78e7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e78e7-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e78e7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e78e7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e78e7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e78e7-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e78e7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e78e7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e78e7-118">E_FAIL</span></span>|<span data-ttu-id="e78e7-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="e78e7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e78e7-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e78e7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e78e7-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e78e7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e78e7-122">Требования</span><span class="sxs-lookup"><span data-stu-id="e78e7-122">Requirements</span></span>  
 <span data-ttu-id="e78e7-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e78e7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e78e7-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e78e7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e78e7-125">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e78e7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e78e7-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e78e7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78e7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e78e7-127">See Also</span></span>  
 [<span data-ttu-id="e78e7-128">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e78e7-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e78e7-129">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e78e7-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="e78e7-130">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e78e7-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="e78e7-131">IHostSemaphore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e78e7-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="e78e7-132">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e78e7-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
