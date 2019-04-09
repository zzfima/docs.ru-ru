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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131967"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="67db1-102">Метод IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="67db1-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="67db1-103">Связывает `ICLRTask` экземпляра с текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="67db1-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67db1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67db1-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67db1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67db1-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="67db1-106">[in] Указатель интерфейса на `ICLRTask` экземпляра должны быть сопоставлены текущим `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="67db1-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67db1-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67db1-107">Return Value</span></span>  
  
|<span data-ttu-id="67db1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67db1-108">HRESULT</span></span>|<span data-ttu-id="67db1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="67db1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67db1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67db1-110">S_OK</span></span>|`SetCLRTask` <span data-ttu-id="67db1-111">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="67db1-111">returned successfully.</span></span>|  
|<span data-ttu-id="67db1-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67db1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67db1-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="67db1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67db1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67db1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67db1-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="67db1-115">The call timed out.</span></span>|  
|<span data-ttu-id="67db1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67db1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67db1-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="67db1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67db1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67db1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67db1-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="67db1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67db1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67db1-120">E_FAIL</span></span>|<span data-ttu-id="67db1-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="67db1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67db1-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="67db1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67db1-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="67db1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67db1-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="67db1-124">Remarks</span></span>  
 <span data-ttu-id="67db1-125">Среда CLR вызывает `SetCLRTask` связываемый `ICLRTask` экземпляра с текущим `IHostTask` экземпляр, который был создан с помощью вызова [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="67db1-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67db1-126">Требования</span><span class="sxs-lookup"><span data-stu-id="67db1-126">Requirements</span></span>  
 <span data-ttu-id="67db1-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67db1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67db1-128">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67db1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67db1-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67db1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="67db1-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="67db1-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67db1-131">См. также</span><span class="sxs-lookup"><span data-stu-id="67db1-131">See also</span></span>

- [<span data-ttu-id="67db1-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="67db1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="67db1-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="67db1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="67db1-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="67db1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="67db1-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="67db1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
