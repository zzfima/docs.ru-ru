---
title: Метод IHostTask::SetCLRTask
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0220a0699e7325c6d81ba3ad4627176640937dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131967"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="3d741-102">Метод IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="3d741-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="3d741-103">Связывает `ICLRTask` экземпляра с текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3d741-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d741-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d741-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d741-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d741-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="3d741-106">[in] Указатель интерфейса на `ICLRTask` экземпляра должны быть сопоставлены текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="3d741-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d741-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d741-107">Return Value</span></span>  
  
|<span data-ttu-id="3d741-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d741-108">HRESULT</span></span>|<span data-ttu-id="3d741-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3d741-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d741-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d741-110">S_OK</span></span>|<span data-ttu-id="3d741-111">`SetCLRTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3d741-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="3d741-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d741-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d741-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3d741-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d741-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d741-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d741-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="3d741-115">The call timed out.</span></span>|  
|<span data-ttu-id="3d741-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d741-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d741-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="3d741-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d741-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d741-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d741-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="3d741-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d741-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d741-120">E_FAIL</span></span>|<span data-ttu-id="3d741-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="3d741-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d741-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3d741-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d741-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3d741-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d741-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d741-124">Remarks</span></span>  
 <span data-ttu-id="3d741-125">Среда CLR вызывает `SetCLRTask` связываемый `ICLRTask` экземпляра с текущим `IHostTask` экземпляр, который был создан с помощью вызова [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="3d741-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d741-126">Требования</span><span class="sxs-lookup"><span data-stu-id="3d741-126">Requirements</span></span>  
 <span data-ttu-id="3d741-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d741-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d741-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d741-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d741-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d741-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d741-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d741-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d741-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3d741-131">See also</span></span>

- [<span data-ttu-id="3d741-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="3d741-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3d741-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="3d741-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3d741-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="3d741-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3d741-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="3d741-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
