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
ms.openlocfilehash: c4eac8abede82915386abc19c4c8389932451df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440380"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="b61b7-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="b61b7-102">IHostGCManager Interface</span></span>
<span data-ttu-id="b61b7-103">Предоставляет методы, уведомляющие основное приложение о событиях в механизме сборки мусора, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b61b7-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="b61b7-104">Участники</span><span class="sxs-lookup"><span data-stu-id="b61b7-104">Members</span></span>  
  
|<span data-ttu-id="b61b7-105">Член</span><span class="sxs-lookup"><span data-stu-id="b61b7-105">Member</span></span>|<span data-ttu-id="b61b7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b61b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b61b7-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="b61b7-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="b61b7-108">Уведомляет узел, что среда CLR возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b61b7-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="b61b7-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="b61b7-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="b61b7-110">Уведомляет узел, что среда CLR приостановила выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b61b7-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="b61b7-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="b61b7-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="b61b7-112">Уведомляет хост, что поток, из которого был выполнен вызов метода готов заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b61b7-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b61b7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b61b7-113">Requirements</span></span>  
 <span data-ttu-id="b61b7-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b61b7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b61b7-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b61b7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b61b7-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b61b7-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b61b7-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b61b7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61b7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b61b7-118">See Also</span></span>  
 [<span data-ttu-id="b61b7-119">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b61b7-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b61b7-120">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b61b7-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b61b7-121">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b61b7-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b61b7-122">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b61b7-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="b61b7-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b61b7-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
