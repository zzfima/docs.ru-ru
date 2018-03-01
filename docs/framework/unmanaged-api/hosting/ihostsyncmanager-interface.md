---
title: "Интерфейс IHostSyncManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="598a0-102">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="598a0-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="598a0-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для создания примитивы синхронизации, вызвав узла вместо использования функций синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="598a0-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="598a0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="598a0-104">Methods</span></span>  
  
|<span data-ttu-id="598a0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="598a0-105">Method</span></span>|<span data-ttu-id="598a0-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="598a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="598a0-107">Метод CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="598a0-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="598a0-108">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="598a0-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="598a0-109">Метод CreateCrst</span><span class="sxs-lookup"><span data-stu-id="598a0-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="598a0-110">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="598a0-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="598a0-111">Метод CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="598a0-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="598a0-112">Создает объект критической секции с прокруток для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="598a0-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="598a0-113">Метод CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="598a0-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="598a0-114">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="598a0-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="598a0-115">Метод CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="598a0-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="598a0-116">Создает объект, отслеживаемый события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="598a0-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="598a0-117">Метод CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="598a0-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="598a0-118">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="598a0-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="598a0-119">Метод CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="598a0-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="598a0-120">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="598a0-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="598a0-121">Метод CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="598a0-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="598a0-122">Создает [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) объекта для среды CLR в качестве семафор для ожидания события.</span><span class="sxs-lookup"><span data-stu-id="598a0-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="598a0-123">Метод SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="598a0-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="598a0-124">Наборы [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) экземпляра для связи с текущим `IHostSyncManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="598a0-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="598a0-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="598a0-125">Remarks</span></span>  
 <span data-ttu-id="598a0-126">Среда CLR обнаруживает реализация `IHostSyncManager` путем вызова [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) метод с `IID` из IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="598a0-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598a0-127">Требования</span><span class="sxs-lookup"><span data-stu-id="598a0-127">Requirements</span></span>  
 <span data-ttu-id="598a0-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="598a0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="598a0-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="598a0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="598a0-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="598a0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="598a0-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="598a0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598a0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="598a0-132">See Also</span></span>  
 [<span data-ttu-id="598a0-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="598a0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="598a0-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="598a0-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
