---
title: Метод ICLRTask::SwitchIn
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938371"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="57999-102">Метод ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="57999-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="57999-103">Уведомляет среду CLR о том, что задача, которую представляет текущий экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) , теперь находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="57999-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57999-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57999-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57999-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="57999-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="57999-106">окне Маркер физического потока, в котором выполняются задачи, представленные текущим `ICLRTask` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="57999-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57999-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57999-107">Return Value</span></span>  
  
|<span data-ttu-id="57999-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57999-108">HRESULT</span></span>|<span data-ttu-id="57999-109">Описание</span><span class="sxs-lookup"><span data-stu-id="57999-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57999-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="57999-110">S_OK</span></span>|<span data-ttu-id="57999-111">`SwitchIn`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="57999-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="57999-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57999-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57999-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="57999-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57999-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57999-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57999-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="57999-115">The call timed out.</span></span>|  
|<span data-ttu-id="57999-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57999-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57999-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="57999-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57999-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57999-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57999-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="57999-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57999-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57999-120">E_FAIL</span></span>|<span data-ttu-id="57999-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="57999-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57999-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="57999-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57999-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="57999-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="57999-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="57999-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="57999-125">`SwitchIn`был вызван без предыдущего вызова [метода Switch](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="57999-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57999-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="57999-126">Remarks</span></span>  
 <span data-ttu-id="57999-127">Параметр представляет собой обработчик для потока операционной системы, в котором запланирована задача, представленная текущим `ICLRTask` экземпляром. `threadHandle`</span><span class="sxs-lookup"><span data-stu-id="57999-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="57999-128">Если в этом потоке возникло олицетворение, то перед переключением в задаче необходимо вызвать метод [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) .</span><span class="sxs-lookup"><span data-stu-id="57999-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57999-129">Вызов метода `SwitchIn` без предыдущего `SwitchOut` вызова завершается ошибкой со значением HRESULT, равным HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="57999-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57999-130">Требования</span><span class="sxs-lookup"><span data-stu-id="57999-130">Requirements</span></span>  
 <span data-ttu-id="57999-131">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57999-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57999-132">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57999-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57999-133">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57999-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57999-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57999-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57999-135">См. также</span><span class="sxs-lookup"><span data-stu-id="57999-135">See also</span></span>

- [<span data-ttu-id="57999-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="57999-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="57999-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="57999-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="57999-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="57999-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="57999-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="57999-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
