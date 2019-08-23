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
ms.openlocfilehash: dbc38d9cf88f2449bbf689e4cf1b4101f47a0577
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943250"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="6f1a5-102">Метод ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="6f1a5-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="6f1a5-103">Возвращает следующий экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , заблокированный для текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f1a5-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f1a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f1a5-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="6f1a5-106">окне Итератор, который был создан с помощью вызова [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="6f1a5-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="6f1a5-107">заполняет Указатель на следующий `IHostTask` объект, ожидающий блокировки, или значение null, если ни одна из задач не ожидает выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f1a5-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f1a5-108">Return Value</span></span>  
  
|<span data-ttu-id="6f1a5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f1a5-109">HRESULT</span></span>|<span data-ttu-id="6f1a5-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6f1a5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f1a5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f1a5-111">S_OK</span></span>|<span data-ttu-id="6f1a5-112">`GetRWLockOwnerNext`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="6f1a5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f1a5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f1a5-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f1a5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f1a5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f1a5-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-116">The call timed out.</span></span>|  
|<span data-ttu-id="6f1a5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f1a5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f1a5-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f1a5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f1a5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f1a5-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f1a5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f1a5-121">E_FAIL</span></span>|<span data-ttu-id="6f1a5-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f1a5-123">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f1a5-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f1a5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f1a5-125">Remarks</span></span>  
 <span data-ttu-id="6f1a5-126">Если `ppOwnerHostTask` параметр имеет значение null, итерация завершается и узел должен вызвать метод [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6f1a5-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f1a5-127">Среда CLR вызывает `AddRef` метод в `IHostTask` , который `ppOwnerHostTask` указывает, чтобы предотвратить выход этой задачи, пока узел удерживает указатель.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="6f1a5-128">Узел должен вызвать `Release` , чтобы уменьшить число ссылок по завершении.</span><span class="sxs-lookup"><span data-stu-id="6f1a5-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f1a5-129">Требования</span><span class="sxs-lookup"><span data-stu-id="6f1a5-129">Requirements</span></span>  
 <span data-ttu-id="6f1a5-130">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f1a5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f1a5-131">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6f1a5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f1a5-132">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6f1a5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f1a5-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f1a5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1a5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6f1a5-134">See also</span></span>

- [<span data-ttu-id="6f1a5-135">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="6f1a5-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6f1a5-136">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6f1a5-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
