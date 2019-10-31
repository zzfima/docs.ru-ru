---
title: Интерфейс IHostGCManager
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 6f7158bcac7ad22647104e2041da959285d2be8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130480"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="0d0d2-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="0d0d2-102">IHostGCManager Interface</span></span>
<span data-ttu-id="0d0d2-103">Предоставляет методы, которые уведомляют узел о событиях в механизме сборки мусора, реализованном средой CLR.</span><span class="sxs-lookup"><span data-stu-id="0d0d2-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="0d0d2-104">Члены</span><span class="sxs-lookup"><span data-stu-id="0d0d2-104">Members</span></span>  
  
|<span data-ttu-id="0d0d2-105">Член</span><span class="sxs-lookup"><span data-stu-id="0d0d2-105">Member</span></span>|<span data-ttu-id="0d0d2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0d0d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d0d2-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="0d0d2-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="0d0d2-108">Уведомляет узел о том, что среда CLR возобновляет выполнение задач в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d0d2-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="0d0d2-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="0d0d2-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="0d0d2-110">Уведомляет узел о том, что среда CLR приостанавливает выполнение задач, для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d0d2-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="0d0d2-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="0d0d2-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="0d0d2-112">Уведомляет узел о том, что поток, из которого был сделан вызов метода, собирается блокироваться для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d0d2-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d0d2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0d0d2-113">Requirements</span></span>  
 <span data-ttu-id="0d0d2-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d0d2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d0d2-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0d0d2-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d0d2-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0d0d2-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d0d2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0d2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0d2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0d0d2-118">See also</span></span>

- [<span data-ttu-id="0d0d2-119">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="0d0d2-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0d0d2-120">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="0d0d2-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0d0d2-121">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="0d0d2-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0d0d2-122">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0d0d2-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="0d0d2-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0d0d2-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
