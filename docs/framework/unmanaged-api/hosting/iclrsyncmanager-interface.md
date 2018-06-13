---
title: Интерфейс ICLRSyncManager
ms.date: 03/30/2017
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
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436485"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="5c5c3-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c5c3-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="5c5c3-103">Определяет методы, позволяющие узла, чтобы получить сведения о запрашиваемых задачах и взаимоблокировки в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c5c3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5c5c3-104">Methods</span></span>  
  
|<span data-ttu-id="5c5c3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5c5c3-105">Method</span></span>|<span data-ttu-id="5c5c3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5c5c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c5c3-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="5c5c3-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="5c5c3-108">Запросы, которые общеязыковой среды выполнения (CLR) создают итератор для узла, который используется для определения набора задач, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="5c5c3-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="5c5c3-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="5c5c3-110">Запросы, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="5c5c3-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="5c5c3-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="5c5c3-112">Возвращает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="5c5c3-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="5c5c3-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="5c5c3-114">Получает следующую задачу, ожидающих блокировки чтения записи.</span><span class="sxs-lookup"><span data-stu-id="5c5c3-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c5c3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5c5c3-115">Requirements</span></span>  
 <span data-ttu-id="5c5c3-116">**Платформы:** разделе [требования к системе для](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5c3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5c3-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c5c3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c5c3-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c5c3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c5c3-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5c3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5c3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5c5c3-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="5c5c3-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5c5c3-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="5c5c3-122">[Управляемые и неуправляемые потоки](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5c5c3-122">[Managed and Unmanaged Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span></span>  
 [<span data-ttu-id="5c5c3-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5c5c3-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
