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
ms.openlocfilehash: d3e4affa363083ce55ac3764c26412a0d60ba3f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763598"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="e6976-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6976-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="e6976-103">Определяет методы, позволяющие узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="e6976-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6976-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e6976-104">Methods</span></span>  
  
|<span data-ttu-id="e6976-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e6976-105">Method</span></span>|<span data-ttu-id="e6976-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e6976-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6976-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="e6976-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="e6976-108">Запросы, которые среда CLR (CLR) создают итератор для узла для определения набора задач, ожидающих блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="e6976-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="e6976-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="e6976-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="e6976-110">Запрашивает, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="e6976-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="e6976-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="e6976-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="e6976-112">Получает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="e6976-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="e6976-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="e6976-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="e6976-114">Получает следующую задачу, ожидающую текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="e6976-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6976-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e6976-115">Requirements</span></span>  
 <span data-ttu-id="e6976-116">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6976-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6976-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6976-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6976-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6976-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6976-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6976-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6976-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e6976-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="e6976-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6976-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="e6976-122">[Управляемые и неуправляемые потоки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e6976-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="e6976-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e6976-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
