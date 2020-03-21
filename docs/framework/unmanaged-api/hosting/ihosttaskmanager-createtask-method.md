---
title: Метод IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177991"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="22b1a-102">Метод IHostTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="22b1a-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="22b1a-103">Запросы на создание узла новой задачи.</span><span class="sxs-lookup"><span data-stu-id="22b1a-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22b1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22b1a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22b1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22b1a-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="22b1a-106">(в) Запрошенный размер, в байтах, запрашиваемого стека, или 0 (ноль) для размера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="22b1a-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="22b1a-107">(в) Указатель на функцию, которую выполняет задача.</span><span class="sxs-lookup"><span data-stu-id="22b1a-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="22b1a-108">(в) Указатель на пользовательские данные, которые должны быть переданы функции, или нулевые, если функция не принимает никаких параметров.</span><span class="sxs-lookup"><span data-stu-id="22b1a-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="22b1a-109">(ваут) Указатель на адрес экземпляра [IHostTask,](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) созданный унизатом, или нулевый, если задача не может быть создана.</span><span class="sxs-lookup"><span data-stu-id="22b1a-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="22b1a-110">Задача остается в приостановленном состоянии до тех пор, пока она явно не запущена вызовом на [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="22b1a-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22b1a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="22b1a-111">Return Value</span></span>  
  
|<span data-ttu-id="22b1a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22b1a-112">HRESULT</span></span>|<span data-ttu-id="22b1a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="22b1a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22b1a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="22b1a-114">S_OK</span></span>|<span data-ttu-id="22b1a-115">`CreateTask`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="22b1a-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="22b1a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22b1a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22b1a-117">Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="22b1a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22b1a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22b1a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22b1a-119">Вызов приурочен.</span><span class="sxs-lookup"><span data-stu-id="22b1a-119">The call timed out.</span></span>|  
|<span data-ttu-id="22b1a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22b1a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22b1a-121">Звонящее не владеет замком.</span><span class="sxs-lookup"><span data-stu-id="22b1a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22b1a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22b1a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22b1a-123">Событие было отменено в то время как заблокированный поток или волокно ждало на нем.</span><span class="sxs-lookup"><span data-stu-id="22b1a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22b1a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22b1a-124">E_FAIL</span></span>|<span data-ttu-id="22b1a-125">Произошел неизвестный катастрофический сбой.</span><span class="sxs-lookup"><span data-stu-id="22b1a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22b1a-126">Когда метод возвращается E_FAIL, CLR больше не используется в процессе.</span><span class="sxs-lookup"><span data-stu-id="22b1a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22b1a-127">Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22b1a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="22b1a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="22b1a-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="22b1a-129">Недостаточно памяти было доступно для создания запрашиваемых задач.</span><span class="sxs-lookup"><span data-stu-id="22b1a-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22b1a-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="22b1a-130">Remarks</span></span>  
 <span data-ttu-id="22b1a-131">CLR требует, `CreateTask` чтобы ухтабыла создала новую задачу.</span><span class="sxs-lookup"><span data-stu-id="22b1a-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="22b1a-132">Хост возвращает указатель `IHostTask` интерфейса в экземпляр.</span><span class="sxs-lookup"><span data-stu-id="22b1a-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="22b1a-133">Возвращалась задача должна оставаться `IHostTask::Start`приостановленной до тех пор, пока она явно не будет запущена вызовом.</span><span class="sxs-lookup"><span data-stu-id="22b1a-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22b1a-134">Требования</span><span class="sxs-lookup"><span data-stu-id="22b1a-134">Requirements</span></span>  
 <span data-ttu-id="22b1a-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22b1a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22b1a-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22b1a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22b1a-137">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22b1a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22b1a-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22b1a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b1a-139">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="22b1a-139">See also</span></span>

- [<span data-ttu-id="22b1a-140">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="22b1a-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="22b1a-141">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="22b1a-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="22b1a-142">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="22b1a-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="22b1a-143">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="22b1a-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
