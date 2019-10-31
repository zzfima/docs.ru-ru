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
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133931"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="745bb-102">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="745bb-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="745bb-103">Определяет методы, позволяющие узлу получать сведения о запрошенных задачах и обнаруживать взаимоблокировки в своей реализации синхронизации.</span><span class="sxs-lookup"><span data-stu-id="745bb-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="745bb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="745bb-104">Methods</span></span>  
  
|<span data-ttu-id="745bb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="745bb-105">Method</span></span>|<span data-ttu-id="745bb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="745bb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="745bb-107">Метод CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="745bb-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="745bb-108">Запрашивает, что среда CLR создает итератор для узла, который будет использоваться для определения набора задач, ожидающих блокировки чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="745bb-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="745bb-109">Метод DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="745bb-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="745bb-110">Запрашивает уничтожение итератора, созданного с помощью вызова `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="745bb-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="745bb-111">Метод GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="745bb-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="745bb-112">Возвращает задачу, которая владеет указанным монитором.</span><span class="sxs-lookup"><span data-stu-id="745bb-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="745bb-113">Метод GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="745bb-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="745bb-114">Возвращает следующую задачу, ожидающую текущую блокировку модуля чтения-записи.</span><span class="sxs-lookup"><span data-stu-id="745bb-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="745bb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="745bb-115">Requirements</span></span>  
 <span data-ttu-id="745bb-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="745bb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="745bb-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="745bb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="745bb-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="745bb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="745bb-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="745bb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745bb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="745bb-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="745bb-121">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="745bb-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="745bb-122">[Управляемая и неуправляемая работа с потоками](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="745bb-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="745bb-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="745bb-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
