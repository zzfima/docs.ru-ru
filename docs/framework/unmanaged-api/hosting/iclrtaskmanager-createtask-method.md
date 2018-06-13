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
ms.openlocfilehash: f731e121324793a027c5977a02e1973b0d6fff20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439652"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="66bb2-102">Метод ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="66bb2-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="66bb2-103">Запрашивает явным образом, что общеязыковой среды выполнения (CLR) создайте новую задачу.</span><span class="sxs-lookup"><span data-stu-id="66bb2-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66bb2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66bb2-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66bb2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66bb2-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="66bb2-106">[out] Указатель на адрес вновь созданного [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), или значение null, если не удается создать задачу.</span><span class="sxs-lookup"><span data-stu-id="66bb2-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66bb2-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66bb2-107">Return Value</span></span>  
  
|<span data-ttu-id="66bb2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66bb2-108">HRESULT</span></span>|<span data-ttu-id="66bb2-109">Описание</span><span class="sxs-lookup"><span data-stu-id="66bb2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66bb2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="66bb2-110">S_OK</span></span>|<span data-ttu-id="66bb2-111">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="66bb2-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="66bb2-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66bb2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66bb2-113">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="66bb2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66bb2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66bb2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66bb2-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="66bb2-115">The call timed out.</span></span>|  
|<span data-ttu-id="66bb2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66bb2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66bb2-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="66bb2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66bb2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66bb2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66bb2-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="66bb2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66bb2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66bb2-120">E_FAIL</span></span>|<span data-ttu-id="66bb2-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="66bb2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66bb2-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="66bb2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66bb2-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66bb2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="66bb2-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="66bb2-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="66bb2-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="66bb2-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66bb2-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="66bb2-126">Remarks</span></span>  
 <span data-ttu-id="66bb2-127">Среда CLR создает новую задачу автоматически при инициализации, когда пользовательский код создает поток с помощью типов в <xref:System.Threading> пространства имен, или если увеличить размер пула потоков.</span><span class="sxs-lookup"><span data-stu-id="66bb2-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="66bb2-128">Задачи также создаются при совершении неуправляемым кодом вызова управляемой функции.</span><span class="sxs-lookup"><span data-stu-id="66bb2-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="66bb2-129">`CreateTask` позволяет узлу совершить явный запрос создания средой CLR новой задачи.</span><span class="sxs-lookup"><span data-stu-id="66bb2-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="66bb2-130">Например узел может вызвать этот метод для предварительной инициализации структур данных.</span><span class="sxs-lookup"><span data-stu-id="66bb2-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66bb2-131">Новая задача возвращается в приостановленном состоянии и остается в приостановленном состоянии, пока узел явно вызывает метод [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="66bb2-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66bb2-132">Требования</span><span class="sxs-lookup"><span data-stu-id="66bb2-132">Requirements</span></span>  
 <span data-ttu-id="66bb2-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66bb2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66bb2-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66bb2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66bb2-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66bb2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66bb2-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66bb2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66bb2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="66bb2-137">See Also</span></span>  
 [<span data-ttu-id="66bb2-138">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="66bb2-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="66bb2-139">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="66bb2-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="66bb2-140">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="66bb2-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="66bb2-141">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="66bb2-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
