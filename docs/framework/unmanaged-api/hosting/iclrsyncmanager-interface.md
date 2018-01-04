---
title: "Интерфейс ICLRSyncManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager
helpviewer_keywords: ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5406a7a2912554552697c11fd7aa7a2c0e643fa0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="ee9ea-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="ee9ea-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="ee9ea-103">Определяет методы, позволяющие узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="ee9ea-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee9ea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ee9ea-104">Methods</span></span>  
  
|<span data-ttu-id="ee9ea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ee9ea-105">Method</span></span>|<span data-ttu-id="ee9ea-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="ee9ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee9ea-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="ee9ea-107">CreateRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="ee9ea-108">Запросы, которые общеязыковой среды выполнения (CLR) создают итератор для узла, который используется для определения набора задач, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="ee9ea-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="ee9ea-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="ee9ea-109">DeleteRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="ee9ea-110">Запросы, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="ee9ea-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="ee9ea-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="ee9ea-111">GetMonitorOwner Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="ee9ea-112">Возвращает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="ee9ea-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="ee9ea-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="ee9ea-113">GetRWLockOwnerNext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="ee9ea-114">Получает следующую задачу, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="ee9ea-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee9ea-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ee9ea-115">Requirements</span></span>  
 <span data-ttu-id="ee9ea-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ea-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee9ea-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ee9ea-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee9ea-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee9ea-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee9ea-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee9ea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee9ea-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ee9ea-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="ee9ea-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="ee9ea-121">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="ee9ea-122">Управляемые и неуправляемые потоки</span><span class="sxs-lookup"><span data-stu-id="ee9ea-122">Managed and Unmanaged Threading</span></span>](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [<span data-ttu-id="ee9ea-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ee9ea-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
