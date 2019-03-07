---
title: Метод IHostTaskManager::GetCurrentTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53227908f263cceeb8677739c0bf5b5ba30cd5e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473985"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="e8360-102">Метод IHostTaskManager::GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="e8360-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="e8360-103">Получает указатель интерфейса на задачу, которая в данный момент в потоке операционной системы, из которого этот вызов выполняется.</span><span class="sxs-lookup"><span data-stu-id="e8360-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8360-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8360-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8360-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8360-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="e8360-106">[out] Указатель на адрес [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, представляющий текущей выполняемой задачи, или значение null, если ни одна задача в данный момент.</span><span class="sxs-lookup"><span data-stu-id="e8360-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8360-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e8360-107">Return Value</span></span>  
  
|<span data-ttu-id="e8360-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8360-108">HRESULT</span></span>|<span data-ttu-id="e8360-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e8360-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e8360-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8360-110">S_OK</span></span>|<span data-ttu-id="e8360-111">`GetCurrentTask` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e8360-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="e8360-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e8360-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e8360-113">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e8360-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e8360-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e8360-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e8360-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e8360-115">The call timed out.</span></span>|  
|<span data-ttu-id="e8360-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e8360-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e8360-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e8360-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e8360-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e8360-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e8360-119">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e8360-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e8360-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e8360-120">E_FAIL</span></span>|<span data-ttu-id="e8360-121">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e8360-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e8360-122">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e8360-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e8360-123">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e8360-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e8360-124">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="e8360-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="e8360-125">`GetCurrentTask` был вызван в потоке операционной системы за пределами элемента узла.</span><span class="sxs-lookup"><span data-stu-id="e8360-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8360-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8360-126">Remarks</span></span>  
 <span data-ttu-id="e8360-127">Можно также задать узел `pTask` параметр значение null, чтобы предотвратить задачи, он не запускали входа в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="e8360-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8360-128">Требования</span><span class="sxs-lookup"><span data-stu-id="e8360-128">Requirements</span></span>  
 <span data-ttu-id="e8360-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8360-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8360-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8360-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8360-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8360-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8360-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8360-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8360-133">См. также</span><span class="sxs-lookup"><span data-stu-id="e8360-133">See also</span></span>
- [<span data-ttu-id="e8360-134">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e8360-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e8360-135">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e8360-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e8360-136">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e8360-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e8360-137">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e8360-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
