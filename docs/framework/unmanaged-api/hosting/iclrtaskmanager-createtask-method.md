---
title: Метод ICLRTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a801afeac690c02ef08652a923c31be14967cdc0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465795"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="afff8-102">Метод ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="afff8-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="afff8-103">Запрашивает явным образом, что общеязыковая среда выполнения (CLR) создайте новую задачу.</span><span class="sxs-lookup"><span data-stu-id="afff8-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afff8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afff8-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afff8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="afff8-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="afff8-106">[out] Указатель на адрес вновь созданного [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), или значение null, если не удалось создать задачу.</span><span class="sxs-lookup"><span data-stu-id="afff8-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afff8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="afff8-107">Return Value</span></span>  
  
|<span data-ttu-id="afff8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="afff8-108">HRESULT</span></span>|<span data-ttu-id="afff8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="afff8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afff8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="afff8-110">S_OK</span></span>|<span data-ttu-id="afff8-111">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="afff8-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="afff8-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="afff8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="afff8-113">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="afff8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="afff8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="afff8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="afff8-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="afff8-115">The call timed out.</span></span>|  
|<span data-ttu-id="afff8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="afff8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="afff8-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="afff8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="afff8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="afff8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="afff8-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="afff8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="afff8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="afff8-120">E_FAIL</span></span>|<span data-ttu-id="afff8-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="afff8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="afff8-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="afff8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="afff8-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="afff8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="afff8-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="afff8-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="afff8-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="afff8-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afff8-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="afff8-126">Remarks</span></span>  
 <span data-ttu-id="afff8-127">Среда CLR создает новую задачу автоматически при инициализации, когда пользовательский код создает поток с помощью типов в <xref:System.Threading> пространства имен, или когда увеличивается размер пула потоков.</span><span class="sxs-lookup"><span data-stu-id="afff8-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="afff8-128">Он также создает задачи, если неуправляемый код вызывает для управляемой функции.</span><span class="sxs-lookup"><span data-stu-id="afff8-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="afff8-129">`CreateTask` позволяет узлу убедитесь, что среда CLR создаст новую задачу явного запроса.</span><span class="sxs-lookup"><span data-stu-id="afff8-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="afff8-130">Например узел может вызывать этот метод для предварительной инициализации структур данных.</span><span class="sxs-lookup"><span data-stu-id="afff8-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="afff8-131">Новая задача возвращается в приостановленном состоянии и остается в узел явным образом вызывает метод [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="afff8-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afff8-132">Требования</span><span class="sxs-lookup"><span data-stu-id="afff8-132">Requirements</span></span>  
 <span data-ttu-id="afff8-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afff8-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afff8-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="afff8-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afff8-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afff8-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afff8-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afff8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afff8-137">См. также</span><span class="sxs-lookup"><span data-stu-id="afff8-137">See also</span></span>
- [<span data-ttu-id="afff8-138">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="afff8-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="afff8-139">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="afff8-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="afff8-140">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="afff8-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="afff8-141">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="afff8-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
