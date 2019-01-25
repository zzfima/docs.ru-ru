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
ms.openlocfilehash: 2d518d5149e43718ae14dcdde96febe63fed7709
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744610"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="5d7bf-102">Метод ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="5d7bf-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="5d7bf-103">Уведомляет общеязыковой среды выполнения (CLR), задачи, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d7bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d7bf-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d7bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d7bf-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="5d7bf-106">[in] Дескриптор физическом потоке, в котором задача, представленная текущим `ICLRTask` выполняется экземпляр.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d7bf-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d7bf-107">Return Value</span></span>  
  
|<span data-ttu-id="5d7bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d7bf-108">HRESULT</span></span>|<span data-ttu-id="5d7bf-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5d7bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d7bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d7bf-110">S_OK</span></span>|<span data-ttu-id="5d7bf-111">`SwitchIn` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="5d7bf-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d7bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d7bf-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d7bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d7bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d7bf-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d7bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d7bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d7bf-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d7bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d7bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d7bf-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d7bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d7bf-120">E_FAIL</span></span>|<span data-ttu-id="5d7bf-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d7bf-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d7bf-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d7bf-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="5d7bf-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="5d7bf-125">`SwitchIn` был вызван без вызова [метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="5d7bf-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d7bf-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d7bf-126">Remarks</span></span>  
 <span data-ttu-id="5d7bf-127">`threadHandle` Параметр представляет дескриптор потока операционной системы, в которой задача, представленная текущим `ICLRTask` экземпляр был запланирован.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="5d7bf-128">Если в данном потоке произошло олицетворение, необходимо вызвать [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) перед переключением в задаче.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d7bf-129">Вызов `SwitchIn` без предыдущими вызовами `SwitchOut` завершается сбоем с HRESULT со значением значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="5d7bf-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d7bf-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5d7bf-130">Requirements</span></span>  
 <span data-ttu-id="5d7bf-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d7bf-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d7bf-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d7bf-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d7bf-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d7bf-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d7bf-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d7bf-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d7bf-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5d7bf-135">See also</span></span>
- [<span data-ttu-id="5d7bf-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="5d7bf-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5d7bf-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d7bf-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5d7bf-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="5d7bf-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5d7bf-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="5d7bf-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
