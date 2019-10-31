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
ms.openlocfilehash: fcb78dd5374ff97f23d7dfea63fe33fa96836958
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124535"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="b5386-102">Метод ICLRTaskManager::CreateTask</span><span class="sxs-lookup"><span data-stu-id="b5386-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="b5386-103">Явно запрашивает создание новой задачи средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b5386-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5386-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5386-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5386-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5386-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="b5386-106">заполняет Указатель на адрес только что созданного файла [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)или значение null, если задачу не удалось создать.</span><span class="sxs-lookup"><span data-stu-id="b5386-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5386-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5386-107">Return Value</span></span>  
  
|<span data-ttu-id="b5386-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5386-108">HRESULT</span></span>|<span data-ttu-id="b5386-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b5386-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5386-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5386-110">S_OK</span></span>|<span data-ttu-id="b5386-111">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b5386-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b5386-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5386-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5386-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b5386-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b5386-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5386-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b5386-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b5386-115">The call timed out.</span></span>|  
|<span data-ttu-id="b5386-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b5386-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b5386-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b5386-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b5386-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b5386-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b5386-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b5386-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b5386-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5386-120">E_FAIL</span></span>|<span data-ttu-id="b5386-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b5386-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b5386-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b5386-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b5386-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b5386-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b5386-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b5386-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b5386-125">Недостаточно памяти для выделения запрошенного ресурса.</span><span class="sxs-lookup"><span data-stu-id="b5386-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5386-126">Заметки</span><span class="sxs-lookup"><span data-stu-id="b5386-126">Remarks</span></span>  
 <span data-ttu-id="b5386-127">Среда CLR автоматически создает новую задачу при инициализации, когда пользовательский код создает поток с помощью типов в пространстве имен <xref:System.Threading> или при увеличении размера пула потоков.</span><span class="sxs-lookup"><span data-stu-id="b5386-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="b5386-128">Он также создает задачи, когда неуправляемый код вызывает управляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="b5386-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="b5386-129">`CreateTask` позволяет узлу выполнить явный запрос о том, что среда CLR создает новую задачу.</span><span class="sxs-lookup"><span data-stu-id="b5386-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="b5386-130">Например, узел может вызвать этот метод для прединициализации структур данных.</span><span class="sxs-lookup"><span data-stu-id="b5386-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b5386-131">Новая задача возвращается в приостановленном состоянии и остается приостановленной до тех пор, пока узел явно не вызывает метод [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="b5386-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5386-132">Требования</span><span class="sxs-lookup"><span data-stu-id="b5386-132">Requirements</span></span>  
 <span data-ttu-id="b5386-133">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5386-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5386-134">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b5386-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5386-135">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b5386-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5386-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5386-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5386-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b5386-137">See also</span></span>

- [<span data-ttu-id="b5386-138">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b5386-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b5386-139">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5386-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b5386-140">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b5386-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b5386-141">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b5386-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
