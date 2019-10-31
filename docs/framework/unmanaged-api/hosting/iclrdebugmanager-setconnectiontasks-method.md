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
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129373"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="6d0c8-102">Метод ICLRDebugManager::SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="6d0c8-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="6d0c8-103">Связывает список экземпляров [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) с идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d0c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d0c8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d0c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d0c8-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6d0c8-106">окне Специфический для узла идентификатор соединения, с которым связывается массив `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="6d0c8-107">окне Число членов `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="6d0c8-108">Это число должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="6d0c8-109">окне Массив `ICLRTask`ных указателей, связываемых с соединением, идентифицируемым `id`.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="6d0c8-110">Этот массив должен содержать по крайней мере один элемент.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d0c8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d0c8-111">Return Value</span></span>  
  
|<span data-ttu-id="6d0c8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d0c8-112">HRESULT</span></span>|<span data-ttu-id="6d0c8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6d0c8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d0c8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d0c8-114">S_OK</span></span>|<span data-ttu-id="6d0c8-115">`SetConnectionTasks` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="6d0c8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d0c8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d0c8-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d0c8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d0c8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d0c8-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-119">The call timed out.</span></span>|  
|<span data-ttu-id="6d0c8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d0c8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d0c8-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d0c8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d0c8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d0c8-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d0c8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d0c8-124">E_FAIL</span></span>|<span data-ttu-id="6d0c8-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d0c8-126">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d0c8-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6d0c8-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6d0c8-128">E_INVALIDARG</span></span>|<span data-ttu-id="6d0c8-129">[Бегинконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) не вызывался с помощью этого значения `id`или `dwCount` или `id` равно нулю, либо один из элементов `ppCLRTask` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d0c8-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="6d0c8-130">Remarks</span></span>  
 <span data-ttu-id="6d0c8-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода: `BeginConnection`, `SetConnectionTasks`и [ендконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)для связывания списков задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6d0c8-132">Эти три метода должны вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="6d0c8-133">Сначала вызывается `BeginConnection`, чтобы установить новое соединение.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="6d0c8-134">`SetConnectionTasks` вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="6d0c8-135">`EndConnection` вызывается Last для удаления связи между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="6d0c8-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d0c8-136">Требования</span><span class="sxs-lookup"><span data-stu-id="6d0c8-136">Requirements</span></span>  
 <span data-ttu-id="6d0c8-137">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d0c8-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d0c8-138">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6d0c8-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d0c8-139">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6d0c8-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d0c8-140">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d0c8-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d0c8-141">См. также</span><span class="sxs-lookup"><span data-stu-id="6d0c8-141">See also</span></span>

- [<span data-ttu-id="6d0c8-142">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6d0c8-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6d0c8-143">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="6d0c8-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="6d0c8-144">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="6d0c8-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="6d0c8-145">Метод EndConnection</span><span class="sxs-lookup"><span data-stu-id="6d0c8-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="6d0c8-146">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="6d0c8-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
