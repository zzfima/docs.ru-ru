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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203097"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="65686-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="65686-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="65686-103">Определяет методы, позволяющие узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="65686-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65686-104">Методы</span><span class="sxs-lookup"><span data-stu-id="65686-104">Methods</span></span>  
  
|<span data-ttu-id="65686-105">Метод</span><span class="sxs-lookup"><span data-stu-id="65686-105">Method</span></span>|<span data-ttu-id="65686-106">Описание</span><span class="sxs-lookup"><span data-stu-id="65686-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65686-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="65686-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="65686-108">Запросы, которые среда CLR (CLR) создают итератор для узла для определения набора задач, ожидающих блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="65686-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="65686-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="65686-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="65686-110">Запрашивает, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="65686-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="65686-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="65686-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="65686-112">Получает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="65686-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="65686-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="65686-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="65686-114">Получает следующую задачу, ожидающую текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="65686-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65686-115">Требования</span><span class="sxs-lookup"><span data-stu-id="65686-115">Requirements</span></span>  
 <span data-ttu-id="65686-116">**Платформы:** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65686-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65686-117">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65686-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65686-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65686-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="65686-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="65686-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="65686-120">См. также</span><span class="sxs-lookup"><span data-stu-id="65686-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="65686-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="65686-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="65686-122">Управляемые и неуправляемые потоки</span><span class="sxs-lookup"><span data-stu-id="65686-122">Managed and Unmanaged Threading</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [<span data-ttu-id="65686-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="65686-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
