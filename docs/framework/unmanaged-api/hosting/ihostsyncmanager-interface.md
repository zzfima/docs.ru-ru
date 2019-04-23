---
title: Интерфейс IHostSyncManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200da8b87b52a29c2b075d1e06929031d3f588b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174230"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="5c2df-102">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c2df-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="5c2df-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для создания примитивы синхронизации, вызвав узла вместо использования функций синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="5c2df-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c2df-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5c2df-104">Methods</span></span>  
  
|<span data-ttu-id="5c2df-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5c2df-105">Method</span></span>|<span data-ttu-id="5c2df-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5c2df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c2df-107">Метод CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="5c2df-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="5c2df-108">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="5c2df-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="5c2df-109">Метод CreateCrst</span><span class="sxs-lookup"><span data-stu-id="5c2df-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="5c2df-110">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5c2df-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="5c2df-111">Метод CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="5c2df-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="5c2df-112">Создает объект критической секции с числом прокруток для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5c2df-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="5c2df-113">Метод CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="5c2df-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="5c2df-114">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="5c2df-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="5c2df-115">Метод CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="5c2df-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="5c2df-116">Создает объект наблюдаемое событие автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="5c2df-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="5c2df-117">Метод CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="5c2df-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="5c2df-118">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="5c2df-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="5c2df-119">Метод CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="5c2df-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="5c2df-120">Создает объект события автоматического сброса для реализации блокировку записи.</span><span class="sxs-lookup"><span data-stu-id="5c2df-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="5c2df-121">Метод CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="5c2df-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="5c2df-122">Создает [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) объект для среды CLR для использования в качестве semaphore для ожидания события.</span><span class="sxs-lookup"><span data-stu-id="5c2df-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="5c2df-123">Метод SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c2df-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="5c2df-124">Наборы [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) экземпляра, связываемый с текущим `IHostSyncManager` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5c2df-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c2df-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c2df-125">Remarks</span></span>  
 <span data-ttu-id="5c2df-126">Среда CLR обнаруживает от реализации узлом `IHostSyncManager` путем вызова [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) метод с `IID` из IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="5c2df-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c2df-127">Требования</span><span class="sxs-lookup"><span data-stu-id="5c2df-127">Requirements</span></span>  
 <span data-ttu-id="5c2df-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c2df-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c2df-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c2df-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c2df-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c2df-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c2df-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c2df-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2df-132">См. также</span><span class="sxs-lookup"><span data-stu-id="5c2df-132">See also</span></span>

- [<span data-ttu-id="5c2df-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c2df-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5c2df-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5c2df-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
