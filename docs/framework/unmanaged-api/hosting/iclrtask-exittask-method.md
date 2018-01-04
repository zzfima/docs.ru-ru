---
title: "Метод ICLRTask::ExitTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.ExitTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff2adafa41ce68a824f6b01888c3565bf054c031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="fb303-102">Метод ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="fb303-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="fb303-103">Уведомляет среду (CLR), задача, представленная текущим [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра заканчивается и пытается корректно задача завершается.</span><span class="sxs-lookup"><span data-stu-id="fb303-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb303-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb303-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fb303-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb303-105">Return Value</span></span>  
  
|<span data-ttu-id="fb303-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb303-106">HRESULT</span></span>|<span data-ttu-id="fb303-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fb303-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb303-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb303-108">S_OK</span></span>|<span data-ttu-id="fb303-109">`ExitTask`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="fb303-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="fb303-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb303-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb303-111">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fb303-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb303-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb303-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb303-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="fb303-113">The call timed out.</span></span>|  
|<span data-ttu-id="fb303-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb303-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb303-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="fb303-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb303-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb303-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb303-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="fb303-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fb303-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb303-118">E_FAIL</span></span>|<span data-ttu-id="fb303-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="fb303-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb303-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fb303-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb303-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fb303-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb303-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb303-122">Remarks</span></span>  
 <span data-ttu-id="fb303-123">`ExitTask`пытается корректно завершить задачи, аналогично для отсоединения поток из библиотеки неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="fb303-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb303-124">Требования</span><span class="sxs-lookup"><span data-stu-id="fb303-124">Requirements</span></span>  
 <span data-ttu-id="fb303-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb303-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb303-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb303-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb303-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb303-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb303-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb303-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb303-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fb303-129">See Also</span></span>  
 [<span data-ttu-id="fb303-130">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="fb303-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fb303-131">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="fb303-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fb303-132">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="fb303-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fb303-133">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="fb303-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
