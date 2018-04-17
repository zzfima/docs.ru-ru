---
title: Интерфейс ICLRSyncManager
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17a1e3073713b54cb7a68e6ba3ef2562d4fbcaeb
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="e3350-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e3350-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="e3350-103">Определяет методы, позволяющие узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e3350-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3350-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e3350-104">Methods</span></span>  
  
|<span data-ttu-id="e3350-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e3350-105">Method</span></span>|<span data-ttu-id="e3350-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e3350-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3350-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="e3350-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="e3350-108">Запросы, которые общеязыковой среды выполнения (CLR) создают итератор для узла, который используется для определения набора задач, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="e3350-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="e3350-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="e3350-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="e3350-110">Запросы, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="e3350-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="e3350-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="e3350-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="e3350-112">Возвращает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="e3350-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="e3350-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="e3350-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="e3350-114">Получает следующую задачу, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="e3350-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3350-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e3350-115">Requirements</span></span>  
 <span data-ttu-id="e3350-116">**Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3350-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3350-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3350-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3350-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3350-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3350-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3350-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3350-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e3350-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="e3350-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e3350-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="e3350-122">[Управляемые и неуправляемые потоки](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e3350-122">[Managed and Unmanaged Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span></span>  
 [<span data-ttu-id="e3350-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e3350-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
