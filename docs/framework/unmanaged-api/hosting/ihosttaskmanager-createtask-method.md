---
title: "Метод IHostTaskManager::CreateTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.CreateTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ba71fcd35b16654ab67db3f657f7821c23b702
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="0f5b3-102">Метод IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="0f5b3-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="0f5b3-103">Запросы на создание новой задачи.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f5b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f5b3-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f5b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f5b3-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="0f5b3-106">[in] Запрошенный размер в байтах, запрошенной стека или 0 (ноль) для размера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="0f5b3-107">[in] Указатель на функцию будет выполнять задача.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="0f5b3-108">[in] Указатель на данные пользователя должны быть переданы функции или значение null, если функция не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="0f5b3-109">[out] Указатель на адрес [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) созданные узла, или значение null, если задача не удается создать экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="0f5b3-110">Задача остается в приостановленном состоянии, пока она запущена явным образом с помощью вызова [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f5b3-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f5b3-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0f5b3-111">Return Value</span></span>  
  
|<span data-ttu-id="0f5b3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f5b3-112">HRESULT</span></span>|<span data-ttu-id="0f5b3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0f5b3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f5b3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f5b3-114">S_OK</span></span>|<span data-ttu-id="0f5b3-115">`CreateTask`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="0f5b3-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f5b3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f5b3-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f5b3-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f5b3-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f5b3-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-119">The call timed out.</span></span>|  
|<span data-ttu-id="0f5b3-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f5b3-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f5b3-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f5b3-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f5b3-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f5b3-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f5b3-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f5b3-124">E_FAIL</span></span>|<span data-ttu-id="0f5b3-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f5b3-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f5b3-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0f5b3-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0f5b3-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0f5b3-129">Не хватает памяти была доступна для создания запрошенной задачи.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f5b3-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="0f5b3-130">Remarks</span></span>  
 <span data-ttu-id="0f5b3-131">Среда CLR вызывает `CreateTask` для запроса создания новой задачи.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="0f5b3-132">Основное приложение возвращает указатель интерфейса `IHostTask` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="0f5b3-133">Возвращаемая задача должна отложен до запускается явным образом с помощью вызова `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="0f5b3-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f5b3-134">Требования</span><span class="sxs-lookup"><span data-stu-id="0f5b3-134">Requirements</span></span>  
 <span data-ttu-id="0f5b3-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f5b3-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f5b3-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f5b3-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f5b3-137">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f5b3-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f5b3-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f5b3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f5b3-139">См. также</span><span class="sxs-lookup"><span data-stu-id="0f5b3-139">See Also</span></span>  
 [<span data-ttu-id="0f5b3-140">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0f5b3-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0f5b3-141">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0f5b3-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0f5b3-142">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0f5b3-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0f5b3-143">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0f5b3-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
