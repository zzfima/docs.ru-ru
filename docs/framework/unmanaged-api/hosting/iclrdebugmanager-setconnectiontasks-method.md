---
title: Метод ICLRDebugManager::SetConnectionTasks
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85746f89347c908e60b77435be1fc4bb097c606a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435599"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="3093e-102">Метод ICLRDebugManager::SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="3093e-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="3093e-103">Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.</span><span class="sxs-lookup"><span data-stu-id="3093e-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3093e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3093e-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3093e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3093e-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="3093e-106">[in] Идентификатор конкретного узла для подключения, с которым необходимо связать `ppCLRTask` массива.</span><span class="sxs-lookup"><span data-stu-id="3093e-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="3093e-107">[in] Количество членов `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="3093e-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="3093e-108">Это число должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="3093e-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="3093e-109">[in] Массив `ICLRTask` указатели, чтобы связать с соединением, обозначенную `id`.</span><span class="sxs-lookup"><span data-stu-id="3093e-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="3093e-110">Этот массив должен содержать хотя бы один член.</span><span class="sxs-lookup"><span data-stu-id="3093e-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3093e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3093e-111">Return Value</span></span>  
  
|<span data-ttu-id="3093e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3093e-112">HRESULT</span></span>|<span data-ttu-id="3093e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3093e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3093e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3093e-114">S_OK</span></span>|<span data-ttu-id="3093e-115">`SetConnectionTasks` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3093e-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="3093e-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3093e-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3093e-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3093e-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3093e-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3093e-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3093e-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3093e-119">The call timed out.</span></span>|  
|<span data-ttu-id="3093e-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3093e-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3093e-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3093e-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3093e-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3093e-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3093e-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3093e-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3093e-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3093e-124">E_FAIL</span></span>|<span data-ttu-id="3093e-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3093e-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3093e-126">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3093e-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3093e-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3093e-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3093e-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3093e-128">E_INVALIDARG</span></span>|<span data-ttu-id="3093e-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) не был вызван с помощью этого значения `id`, или `dwCount` или `id` равняется нулю или одному из элементов `ppCLRTask` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="3093e-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3093e-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="3093e-130">Remarks</span></span>  
 <span data-ttu-id="3093e-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода `BeginConnection`, `SetConnectionTasks`, и [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), для связывания списки задач с идентификаторы и понятные имена.</span><span class="sxs-lookup"><span data-stu-id="3093e-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3093e-132">Эти три метода вызываются в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="3093e-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="3093e-133">`BeginConnection` Сначала вызывается для установления нового подключения.</span><span class="sxs-lookup"><span data-stu-id="3093e-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="3093e-134">`SetConnectionTasks` вызывается Далее необходимо предоставить набор задач, которые необходимо связать с подключением.</span><span class="sxs-lookup"><span data-stu-id="3093e-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="3093e-135">`EndConnection` вызывается для удаления связи между списком задач и идентификатором и понятное имя. Однако вызовы других подключений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="3093e-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3093e-136">Требования</span><span class="sxs-lookup"><span data-stu-id="3093e-136">Requirements</span></span>  
 <span data-ttu-id="3093e-137">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3093e-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3093e-138">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3093e-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3093e-139">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3093e-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3093e-140">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3093e-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3093e-141">См. также</span><span class="sxs-lookup"><span data-stu-id="3093e-141">See Also</span></span>  
 [<span data-ttu-id="3093e-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3093e-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3093e-143">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="3093e-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="3093e-144">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="3093e-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="3093e-145">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="3093e-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="3093e-146">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="3093e-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
