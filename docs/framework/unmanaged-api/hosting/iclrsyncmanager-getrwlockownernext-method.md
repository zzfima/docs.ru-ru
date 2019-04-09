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
ms.openlocfilehash: d3efe80c0442e765274b309e39a79cc867676043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169654"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="a0205-102">Метод ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="a0205-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="a0205-103">Получает следующий [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр, который блокируется на текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="a0205-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0205-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0205-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0205-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0205-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="a0205-106">[in] Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="a0205-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="a0205-107">[out] Указатель на следующий `IHostTask` , ожидающий блокировки, или значение null, если ни одна задача находится в состоянии ожидания.</span><span class="sxs-lookup"><span data-stu-id="a0205-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0205-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0205-108">Return Value</span></span>  
  
|<span data-ttu-id="a0205-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0205-109">HRESULT</span></span>|<span data-ttu-id="a0205-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a0205-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0205-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0205-111">S_OK</span></span>|`GetRWLockOwnerNext` <span data-ttu-id="a0205-112">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a0205-112">returned successfully.</span></span>|  
|<span data-ttu-id="a0205-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0205-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0205-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0205-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0205-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0205-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0205-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a0205-116">The call timed out.</span></span>|  
|<span data-ttu-id="a0205-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0205-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0205-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a0205-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0205-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0205-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0205-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a0205-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0205-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0205-121">E_FAIL</span></span>|<span data-ttu-id="a0205-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a0205-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0205-123">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0205-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0205-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0205-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0205-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0205-125">Remarks</span></span>  
 <span data-ttu-id="a0205-126">Если `ppOwnerHostTask` имеет значение null, операция прервана итерации, и узел должен вызывать [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a0205-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0205-127">Среда CLR вызывает `AddRef` на `IHostTask` к которому `ppOwnerHostTask` точки для предотвращения этой задачи выход из узла удерживает указатель.</span><span class="sxs-lookup"><span data-stu-id="a0205-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="a0205-128">Узел должен вызвать метод `Release` для уменьшения числа ссылок при его завершении.</span><span class="sxs-lookup"><span data-stu-id="a0205-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0205-129">Требования</span><span class="sxs-lookup"><span data-stu-id="a0205-129">Requirements</span></span>  
 <span data-ttu-id="a0205-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0205-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0205-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0205-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0205-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0205-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a0205-133">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a0205-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a0205-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a0205-134">See also</span></span>

- [<span data-ttu-id="a0205-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0205-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a0205-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0205-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
