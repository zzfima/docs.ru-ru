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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eaf5a0061b068d9adea3f6aeb28f9b6bb20c3174
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710263"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="1dd1a-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="1dd1a-102">IHostGCManager Interface</span></span>
<span data-ttu-id="1dd1a-103">Предоставляет методы, которые уведомить узел событий в механизм сборки мусора, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="1dd1a-104">Участники</span><span class="sxs-lookup"><span data-stu-id="1dd1a-104">Members</span></span>  
  
|<span data-ttu-id="1dd1a-105">Член</span><span class="sxs-lookup"><span data-stu-id="1dd1a-105">Member</span></span>|<span data-ttu-id="1dd1a-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="1dd1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1dd1a-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="1dd1a-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="1dd1a-108">Уведомляет основное приложение, что среда CLR возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="1dd1a-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="1dd1a-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="1dd1a-110">Уведомляет основное приложение, что CLR приостанавливает выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="1dd1a-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="1dd1a-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="1dd1a-112">Уведомляет основное приложение, что поток, из которого был вызван метод собираетесь заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="1dd1a-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1dd1a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1dd1a-113">Requirements</span></span>  
 <span data-ttu-id="1dd1a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dd1a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dd1a-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1dd1a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1dd1a-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1dd1a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dd1a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dd1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dd1a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd1a-118">See also</span></span>
- [<span data-ttu-id="1dd1a-119">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1dd1a-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1dd1a-120">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1dd1a-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1dd1a-121">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1dd1a-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1dd1a-122">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1dd1a-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="1dd1a-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1dd1a-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
