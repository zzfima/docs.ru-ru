---
title: "Метод ICLRTask::SwitchIn"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e99fc43dea70d456bbaab9bba63e5a018e9e9201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="2a835-102">Метод ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="2a835-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="2a835-103">Уведомляет общеязыковой среды выполнения (CLR), задача, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="2a835-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a835-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a835-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a835-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a835-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="2a835-106">[in] Дескриптор физическом потоке, в котором задача, представленная текущим `ICLRTask` выполняется экземпляр.</span><span class="sxs-lookup"><span data-stu-id="2a835-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a835-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a835-107">Return Value</span></span>  
  
|<span data-ttu-id="2a835-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a835-108">HRESULT</span></span>|<span data-ttu-id="2a835-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2a835-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a835-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a835-110">S_OK</span></span>|<span data-ttu-id="2a835-111">`SwitchIn`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2a835-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="2a835-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a835-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a835-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2a835-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a835-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a835-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a835-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="2a835-115">The call timed out.</span></span>|  
|<span data-ttu-id="2a835-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a835-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a835-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="2a835-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a835-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a835-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a835-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="2a835-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a835-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a835-120">E_FAIL</span></span>|<span data-ttu-id="2a835-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="2a835-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a835-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2a835-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a835-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2a835-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2a835-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2a835-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="2a835-125">`SwitchIn`был вызван без вызова [метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="2a835-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a835-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a835-126">Remarks</span></span>  
 <span data-ttu-id="2a835-127">`threadHandle` Параметр представляет дескриптор потока операционной системы, в которой задача, представленная текущим `ICLRTask` экземпляр был запланирован.</span><span class="sxs-lookup"><span data-stu-id="2a835-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="2a835-128">Если в этом потоке произошло олицетворение, следует вызвать [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) перед переключением в задаче.</span><span class="sxs-lookup"><span data-stu-id="2a835-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a835-129">Вызов `SwitchIn` без предыдущими вызовами метода `SwitchOut` завершается сбоем с HRESULT со значением значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="2a835-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a835-130">Требования</span><span class="sxs-lookup"><span data-stu-id="2a835-130">Requirements</span></span>  
 <span data-ttu-id="2a835-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a835-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a835-132">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a835-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a835-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a835-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a835-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a835-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a835-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2a835-135">See Also</span></span>  
 [<span data-ttu-id="2a835-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2a835-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2a835-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2a835-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2a835-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2a835-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2a835-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2a835-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
