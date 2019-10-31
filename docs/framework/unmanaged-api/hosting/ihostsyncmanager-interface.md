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
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132626"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="0721d-102">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0721d-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="0721d-103">Предоставляет методы, позволяющие среде CLR создавать примитивы синхронизации путем вызова узла вместо использования функций синхронизации Win32.</span><span class="sxs-lookup"><span data-stu-id="0721d-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0721d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0721d-104">Methods</span></span>  
  
|<span data-ttu-id="0721d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0721d-105">Method</span></span>|<span data-ttu-id="0721d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0721d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0721d-107">Метод CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0721d-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="0721d-108">Создает объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="0721d-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="0721d-109">Метод CreateCrst</span><span class="sxs-lookup"><span data-stu-id="0721d-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="0721d-110">Создает объект критической секции для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0721d-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="0721d-111">Метод CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="0721d-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="0721d-112">Создает объект критической секции с количеством счетчиков для синхронизации.</span><span class="sxs-lookup"><span data-stu-id="0721d-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="0721d-113">Метод CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="0721d-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="0721d-114">Создает объект события ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="0721d-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="0721d-115">Метод CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="0721d-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="0721d-116">Создает Отслеживаемый объект события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="0721d-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="0721d-117">Метод CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="0721d-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="0721d-118">Создает объект события ручного сброса для реализации блокировки чтения.</span><span class="sxs-lookup"><span data-stu-id="0721d-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="0721d-119">Метод CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="0721d-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="0721d-120">Создает объект события автоматического сброса для реализации блокировки модуля записи.</span><span class="sxs-lookup"><span data-stu-id="0721d-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="0721d-121">Метод CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="0721d-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="0721d-122">Создает объект [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) для среды CLR, который будет использоваться в качестве семафора для событий ожидания.</span><span class="sxs-lookup"><span data-stu-id="0721d-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="0721d-123">Метод SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0721d-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="0721d-124">Задает экземпляр [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) , связываемый с текущим экземпляром `IHostSyncManager`.</span><span class="sxs-lookup"><span data-stu-id="0721d-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0721d-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="0721d-125">Remarks</span></span>  
 <span data-ttu-id="0721d-126">Среда CLR обнаруживает реализацию `IHostSyncManager` узла, вызывая метод [IHostControl:: жесостманажер](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) с `IID` IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="0721d-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0721d-127">Требования</span><span class="sxs-lookup"><span data-stu-id="0721d-127">Requirements</span></span>  
 <span data-ttu-id="0721d-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0721d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0721d-129">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0721d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0721d-130">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0721d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0721d-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0721d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0721d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="0721d-132">See also</span></span>

- [<span data-ttu-id="0721d-133">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0721d-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0721d-134">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0721d-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
