---
title: "Метод ICLRTask::SwitchOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchOut
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82fffd5de9735db51d9ea5f417c745736b98b53d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="03163-102">Метод ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="03163-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="03163-103">Уведомляет среду (CLR), задача, представленная текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляр больше не находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="03163-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03163-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03163-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="03163-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03163-105">Return Value</span></span>  
  
|<span data-ttu-id="03163-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03163-106">HRESULT</span></span>|<span data-ttu-id="03163-107">Описание</span><span class="sxs-lookup"><span data-stu-id="03163-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03163-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="03163-108">S_OK</span></span>|<span data-ttu-id="03163-109">`SwitchOut`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="03163-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="03163-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03163-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03163-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="03163-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03163-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03163-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03163-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="03163-113">The call timed out.</span></span>|  
|<span data-ttu-id="03163-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03163-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03163-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="03163-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03163-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03163-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03163-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="03163-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03163-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03163-118">E_FAIL</span></span>|<span data-ttu-id="03163-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="03163-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03163-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="03163-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03163-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03163-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03163-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="03163-122">Remarks</span></span>  
 <span data-ttu-id="03163-123">Узел вызывает `SwitchOut` сообщать среде CLR, временно приостановила выполнение задачи, текущий `ICLRTask` представляет экземпляр сервера и спланирует задачи.</span><span class="sxs-lookup"><span data-stu-id="03163-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03163-124">Требования</span><span class="sxs-lookup"><span data-stu-id="03163-124">Requirements</span></span>  
 <span data-ttu-id="03163-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03163-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03163-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03163-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03163-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03163-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03163-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03163-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03163-129">См. также</span><span class="sxs-lookup"><span data-stu-id="03163-129">See Also</span></span>  
 [<span data-ttu-id="03163-130">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03163-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="03163-131">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03163-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="03163-132">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03163-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="03163-133">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03163-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
