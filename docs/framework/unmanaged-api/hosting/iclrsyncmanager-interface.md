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
ms.openlocfilehash: ede896cdb93217fcfba9d66ed7102bcc1ba762e9
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50041834"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="255da-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="255da-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="255da-103">Определяет методы, позволяющие узла для получения сведений о запрошенных задач и для выявления взаимоблокировок в реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="255da-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="255da-104">Методы</span><span class="sxs-lookup"><span data-stu-id="255da-104">Methods</span></span>  
  
|<span data-ttu-id="255da-105">Метод</span><span class="sxs-lookup"><span data-stu-id="255da-105">Method</span></span>|<span data-ttu-id="255da-106">Описание</span><span class="sxs-lookup"><span data-stu-id="255da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="255da-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="255da-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="255da-108">Запросы, которые среда CLR (CLR) создают итератор для узла для определения набора задач, ожидающих блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="255da-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="255da-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="255da-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="255da-110">Запрашивает, что среда CLR уничтожить итератор, который был создан с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="255da-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="255da-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="255da-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="255da-112">Получает задачу, которой принадлежит указанный монитор.</span><span class="sxs-lookup"><span data-stu-id="255da-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="255da-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="255da-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="255da-114">Получает следующую задачу, ожидающую текущей блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="255da-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="255da-115">Требования</span><span class="sxs-lookup"><span data-stu-id="255da-115">Requirements</span></span>  
 <span data-ttu-id="255da-116">**Платформы:** см. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="255da-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="255da-117">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="255da-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="255da-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="255da-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="255da-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="255da-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="255da-120">См. также</span><span class="sxs-lookup"><span data-stu-id="255da-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="255da-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="255da-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="255da-122">[Управляемые и неуправляемые потоки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="255da-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>  
 [<span data-ttu-id="255da-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="255da-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
