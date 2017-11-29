---
title: "Метод ICLRSyncManager::CreateRWLockOwnerIterator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.CreateRWLockOwnerIterator
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f153550544a8e7622ea3cec0273ff9a97a99f91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="f2ee7-102">Метод ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="f2ee7-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="f2ee7-103">Запросы, которые общеязыковой среды выполнения (CLR) создают итератор для узла, который используется для определения набора задач, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ee7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2ee7-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2ee7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2ee7-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="f2ee7-106">[in] Файл cookie, связанные с блокировкой требуемой чтения записи.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="f2ee7-107">[out] Указатель на итератор, который может быть передан [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) и [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) методы.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2ee7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2ee7-108">Return Value</span></span>  
  
|<span data-ttu-id="f2ee7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2ee7-109">HRESULT</span></span>|<span data-ttu-id="f2ee7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f2ee7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2ee7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2ee7-111">S_OK</span></span>|<span data-ttu-id="f2ee7-112">`CreateRWLockOwnerIterator`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="f2ee7-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2ee7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2ee7-114">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2ee7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2ee7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2ee7-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-116">The call timed out.</span></span>|  
|<span data-ttu-id="f2ee7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2ee7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2ee7-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2ee7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2ee7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2ee7-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2ee7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2ee7-121">E_FAIL</span></span>|<span data-ttu-id="f2ee7-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2ee7-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2ee7-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f2ee7-125">ЗНАЧЕНИЕ HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="f2ee7-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="f2ee7-126">`CreateRWLockOwnerIterator`был вызван в потоке, который выполняется в данный момент управляемый код.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2ee7-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2ee7-127">Remarks</span></span>  
 <span data-ttu-id="f2ee7-128">Узлы обычно вызывается `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, и `GetRWLockOwnerNext` методов во время обнаружения взаимоблокировки.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="f2ee7-129">Основное приложение отвечает за блокировку чтения записи все еще действует, так как среда CLR не предпринимает попытку сохранения блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="f2ee7-130">Несколько стратегий доступны для узла обеспечить допустимость блокировки.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="f2ee7-131">Узел может блокировать вызовы снятия блокировки чтения записи (например, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) гарантируя, что этот блок не вызовет взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="f2ee7-132">Узел может блокировать выход из режима ожидания для объекта события, связанного с блокировкой чтения записи, повторно обеспечение этот блок не вызовет взаимоблокировку.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2ee7-133">`CreateRWLockOwnerIterator`должен вызываться только для потоков, которые в данный момент неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f2ee7-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ee7-134">Требования</span><span class="sxs-lookup"><span data-stu-id="f2ee7-134">Requirements</span></span>  
 <span data-ttu-id="f2ee7-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ee7-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ee7-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2ee7-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2ee7-137">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2ee7-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2ee7-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ee7-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ee7-139">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ee7-139">See Also</span></span>  
 [<span data-ttu-id="f2ee7-140">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f2ee7-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f2ee7-141">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f2ee7-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
