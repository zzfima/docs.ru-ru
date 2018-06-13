---
title: Метод ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4725feff4645ec207be6e6afc7d1e1d38eca36ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435214"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="903f5-102">Метод ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="903f5-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="903f5-103">Получает следующий [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, который блокируется блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="903f5-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="903f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="903f5-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="903f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="903f5-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="903f5-106">[in] Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="903f5-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="903f5-107">[out] Указатель на следующий `IHostTask` ожидает блокировки, или значение null, если задача не находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="903f5-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="903f5-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="903f5-108">Return Value</span></span>  
  
|<span data-ttu-id="903f5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="903f5-109">HRESULT</span></span>|<span data-ttu-id="903f5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="903f5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="903f5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="903f5-111">S_OK</span></span>|<span data-ttu-id="903f5-112">`GetRWLockOwnerNext` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="903f5-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="903f5-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="903f5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="903f5-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="903f5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="903f5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="903f5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="903f5-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="903f5-116">The call timed out.</span></span>|  
|<span data-ttu-id="903f5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="903f5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="903f5-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="903f5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="903f5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="903f5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="903f5-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="903f5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="903f5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="903f5-121">E_FAIL</span></span>|<span data-ttu-id="903f5-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="903f5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="903f5-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="903f5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="903f5-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="903f5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="903f5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="903f5-125">Remarks</span></span>  
 <span data-ttu-id="903f5-126">Если `ppOwnerHostTask` имеет значение null, после завершения итерации, и узел должен вызывать [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="903f5-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="903f5-127">Среда CLR вызывает `AddRef` на `IHostTask` к которому `ppOwnerHostTask` точки для предотвращения этой задачи выход из узла удерживает указатель.</span><span class="sxs-lookup"><span data-stu-id="903f5-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="903f5-128">Узел должен вызвать метод `Release` для уменьшения числа ссылок при его завершении.</span><span class="sxs-lookup"><span data-stu-id="903f5-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="903f5-129">Требования</span><span class="sxs-lookup"><span data-stu-id="903f5-129">Requirements</span></span>  
 <span data-ttu-id="903f5-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="903f5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="903f5-131">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="903f5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="903f5-132">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="903f5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="903f5-133">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="903f5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903f5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="903f5-134">See Also</span></span>  
 [<span data-ttu-id="903f5-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="903f5-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="903f5-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="903f5-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
