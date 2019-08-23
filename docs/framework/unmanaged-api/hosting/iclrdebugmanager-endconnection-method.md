---
title: Метод ICLRDebugManager::EndConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2af6970907eb9895750ca58065b2e0cb735cea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969407"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="5876e-102">Метод ICLRDebugManager::EndConnection</span><span class="sxs-lookup"><span data-stu-id="5876e-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="5876e-103">Удаляет связь между списком задач и идентификатором и понятным именем.</span><span class="sxs-lookup"><span data-stu-id="5876e-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5876e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5876e-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5876e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5876e-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="5876e-106">окне Специфический для узла идентификатор соединения и связанный список задач среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5876e-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5876e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5876e-107">Return Value</span></span>  
  
|<span data-ttu-id="5876e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5876e-108">HRESULT</span></span>|<span data-ttu-id="5876e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5876e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5876e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5876e-110">S_OK</span></span>|<span data-ttu-id="5876e-111">`EndConnection`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="5876e-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="5876e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5876e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5876e-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5876e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5876e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5876e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5876e-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5876e-115">The call timed out.</span></span>|  
|<span data-ttu-id="5876e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5876e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5876e-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5876e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5876e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5876e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5876e-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5876e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5876e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5876e-120">E_FAIL</span></span>|<span data-ttu-id="5876e-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5876e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5876e-122">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5876e-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5876e-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5876e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5876e-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5876e-124">E_INVALIDARG</span></span>|<span data-ttu-id="5876e-125">[Бегинконнектион](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) никогда не вызывался `dwConnectionId`с помощью `dwConnectionId` , или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="5876e-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5876e-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5876e-126">Remarks</span></span>  
 <span data-ttu-id="5876e-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) предоставляет три метода, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)и `EndConnection`, для связывания списков задач с идентификаторами и понятными именами.</span><span class="sxs-lookup"><span data-stu-id="5876e-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5876e-128">Эти три метода должны вызываться в определенном порядке для каждого набора задач.</span><span class="sxs-lookup"><span data-stu-id="5876e-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="5876e-129">`BeginConnection`вызывается первым для установления нового соединения.</span><span class="sxs-lookup"><span data-stu-id="5876e-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="5876e-130">`SetConnectionTasks`вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением.</span><span class="sxs-lookup"><span data-stu-id="5876e-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="5876e-131">`EndConnection`вызывается последним, чтобы удалить связь между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="5876e-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5876e-132">Требования</span><span class="sxs-lookup"><span data-stu-id="5876e-132">Requirements</span></span>  
 <span data-ttu-id="5876e-133">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5876e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5876e-134">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5876e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5876e-135">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5876e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5876e-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5876e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5876e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="5876e-137">See also</span></span>

- [<span data-ttu-id="5876e-138">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5876e-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5876e-139">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="5876e-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="5876e-140">Метод BeginConnection</span><span class="sxs-lookup"><span data-stu-id="5876e-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="5876e-141">Метод SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="5876e-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="5876e-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="5876e-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
