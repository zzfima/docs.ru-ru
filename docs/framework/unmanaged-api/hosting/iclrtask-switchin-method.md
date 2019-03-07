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
ms.openlocfilehash: b0adee689949b4e3303d8921a826cdec56cc1b3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484892"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="9aaef-102">Метод ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="9aaef-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="9aaef-103">Уведомляет общеязыковой среды выполнения (CLR), задачи, текущий [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) представляет экземпляр находится в рабочем состоянии.</span><span class="sxs-lookup"><span data-stu-id="9aaef-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aaef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9aaef-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aaef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9aaef-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="9aaef-106">[in] Дескриптор физическом потоке, в котором задача, представленная текущим `ICLRTask` выполняется экземпляр.</span><span class="sxs-lookup"><span data-stu-id="9aaef-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9aaef-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9aaef-107">Return Value</span></span>  
  
|<span data-ttu-id="9aaef-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9aaef-108">HRESULT</span></span>|<span data-ttu-id="9aaef-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9aaef-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9aaef-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9aaef-110">S_OK</span></span>|<span data-ttu-id="9aaef-111">`SwitchIn` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9aaef-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="9aaef-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9aaef-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9aaef-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9aaef-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9aaef-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9aaef-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9aaef-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9aaef-115">The call timed out.</span></span>|  
|<span data-ttu-id="9aaef-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9aaef-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9aaef-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9aaef-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9aaef-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9aaef-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9aaef-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9aaef-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9aaef-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9aaef-120">E_FAIL</span></span>|<span data-ttu-id="9aaef-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9aaef-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9aaef-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9aaef-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9aaef-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9aaef-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9aaef-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="9aaef-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="9aaef-125">`SwitchIn` был вызван без вызова [метод SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="9aaef-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aaef-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="9aaef-126">Remarks</span></span>  
 <span data-ttu-id="9aaef-127">`threadHandle` Параметр представляет дескриптор потока операционной системы, в которой задача, представленная текущим `ICLRTask` экземпляр был запланирован.</span><span class="sxs-lookup"><span data-stu-id="9aaef-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="9aaef-128">Если в данном потоке произошло олицетворение, необходимо вызвать [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) перед переключением в задаче.</span><span class="sxs-lookup"><span data-stu-id="9aaef-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aaef-129">Вызов `SwitchIn` без предыдущими вызовами `SwitchOut` завершается сбоем с HRESULT со значением значение HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="9aaef-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aaef-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9aaef-130">Requirements</span></span>  
 <span data-ttu-id="9aaef-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aaef-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aaef-132">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9aaef-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9aaef-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9aaef-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9aaef-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aaef-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aaef-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9aaef-135">See also</span></span>
- [<span data-ttu-id="9aaef-136">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="9aaef-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9aaef-137">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="9aaef-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9aaef-138">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="9aaef-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9aaef-139">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="9aaef-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
