---
title: "Метод ICLRTask::Reset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="d444d-102">Метод ICLRTask::Reset</span><span class="sxs-lookup"><span data-stu-id="d444d-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="d444d-103">Информирует общеязыковой среды выполнения (CLR), узел завершения задачи что позволяет повторно использовать текущий CLR [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра для представления другой задачи.</span><span class="sxs-lookup"><span data-stu-id="d444d-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d444d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d444d-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d444d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d444d-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="d444d-106">[in] `true`, если среда выполнения должна сбросить все связанные с потоками статического значения в дополнение к безопасности и языковой стандарт сведения, связанные с текущим `ICLRTask` экземпляра; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="d444d-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d444d-107">Если значение равно `true`, среда выполнения сбрасывает данные, хранящиеся с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span><span class="sxs-lookup"><span data-stu-id="d444d-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d444d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d444d-108">Return Value</span></span>  
  
|<span data-ttu-id="d444d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d444d-109">HRESULT</span></span>|<span data-ttu-id="d444d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d444d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d444d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d444d-111">S_OK</span></span>|<span data-ttu-id="d444d-112">`Reset`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d444d-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d444d-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d444d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d444d-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d444d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d444d-115">успешно</span><span class="sxs-lookup"><span data-stu-id="d444d-115">successfully</span></span>|  
|<span data-ttu-id="d444d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d444d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d444d-117">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d444d-117">The call timed out.</span></span>|  
|<span data-ttu-id="d444d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d444d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d444d-119">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d444d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d444d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d444d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d444d-121">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d444d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d444d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d444d-122">E_FAIL</span></span>|<span data-ttu-id="d444d-123">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d444d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d444d-124">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d444d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d444d-125">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d444d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d444d-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d444d-126">Remarks</span></span>  
 <span data-ttu-id="d444d-127">Среда CLR может повторно использовать ранее созданную `ICLRTask` экземпляров, чтобы избежать издержек по несколько раз, каждый раз, он должен новой задачи, создание новых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d444d-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="d444d-128">Узел включает эту функцию, вызвав `ICLRTask::Reset` вместо [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) после его завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="d444d-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="d444d-129">В следующем списке перечислены обычный жизненный цикл `ICLRTask` экземпляр:</span><span class="sxs-lookup"><span data-stu-id="d444d-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="d444d-130">Среда выполнения создает новый `ICLRTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d444d-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="d444d-131">Среда выполнения вызывает метод [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) получить ссылку на текущую задачу узла.</span><span class="sxs-lookup"><span data-stu-id="d444d-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="d444d-132">Среда выполнения вызывает метод [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) необходимо связать новый экземпляр с задачей узла.</span><span class="sxs-lookup"><span data-stu-id="d444d-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="d444d-133">Задача выполняет и завершается.</span><span class="sxs-lookup"><span data-stu-id="d444d-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="d444d-134">Узел уничтожает задачи путем вызова `ICLRTask::ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="d444d-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="d444d-135">`Reset`изменяет этот сценарий следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d444d-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="d444d-136">В шаге 5 выше, основное приложение вызывает `Reset` для сброса задачи в исходное состояние и затем отсоединяет `ICLRTask` экземпляр, связанный с ним из [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d444d-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="d444d-137">При необходимости также можно кэшировать узла `IHostTask` экземпляра для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="d444d-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="d444d-138">В шаге 1 выше, среда выполнения извлекает перезапущен `ICLRTask` из кэша вместо создания нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d444d-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="d444d-139">Такой подход удобно использовать, когда узел также имеет пул повторно используемых рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="d444d-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="d444d-140">Когда узел Удаляет один из его `IHostTask` экземпляры, она окончательно удаляет соответствующие `ICLRTask` путем вызова `ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="d444d-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d444d-141">Требования</span><span class="sxs-lookup"><span data-stu-id="d444d-141">Requirements</span></span>  
 <span data-ttu-id="d444d-142">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d444d-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d444d-143">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d444d-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d444d-144">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d444d-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d444d-145">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d444d-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d444d-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d444d-146">See Also</span></span>  
 [<span data-ttu-id="d444d-147">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d444d-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d444d-148">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d444d-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d444d-149">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="d444d-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d444d-150">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d444d-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
