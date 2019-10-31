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
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121367"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="c0f82-102">Метод IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="c0f82-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="c0f82-103">Связывает экземпляр `ICLRTask` с текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c0f82-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0f82-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0f82-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0f82-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="c0f82-106">окне Указатель интерфейса на экземпляр `ICLRTask`, который должен быть связан с текущим экземпляром `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="c0f82-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0f82-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0f82-107">Return Value</span></span>  
  
|<span data-ttu-id="c0f82-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0f82-108">HRESULT</span></span>|<span data-ttu-id="c0f82-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c0f82-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0f82-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0f82-110">S_OK</span></span>|<span data-ttu-id="c0f82-111">`SetCLRTask` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="c0f82-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="c0f82-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0f82-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c0f82-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c0f82-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c0f82-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c0f82-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c0f82-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="c0f82-115">The call timed out.</span></span>|  
|<span data-ttu-id="c0f82-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c0f82-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c0f82-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="c0f82-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c0f82-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c0f82-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c0f82-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="c0f82-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c0f82-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0f82-120">E_FAIL</span></span>|<span data-ttu-id="c0f82-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c0f82-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c0f82-122">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c0f82-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c0f82-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c0f82-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f82-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0f82-124">Remarks</span></span>  
 <span data-ttu-id="c0f82-125">Среда CLR вызывает `SetCLRTask`, чтобы связать экземпляр `ICLRTask` с текущим экземпляром `IHostTask`, который был создан путем вызова [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="c0f82-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f82-126">Требования</span><span class="sxs-lookup"><span data-stu-id="c0f82-126">Requirements</span></span>  
 <span data-ttu-id="c0f82-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0f82-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f82-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c0f82-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0f82-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c0f82-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0f82-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0f82-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f82-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c0f82-131">See also</span></span>

- [<span data-ttu-id="c0f82-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c0f82-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c0f82-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c0f82-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c0f82-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="c0f82-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c0f82-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c0f82-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
