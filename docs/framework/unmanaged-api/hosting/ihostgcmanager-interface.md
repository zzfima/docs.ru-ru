---
title: "Интерфейс IHostGCManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager
helpviewer_keywords: IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7452f49df6970bf2ca49781f6a38874186bec64f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="4acf5-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="4acf5-102">IHostGCManager Interface</span></span>
<span data-ttu-id="4acf5-103">Предоставляет методы, уведомляющие основное приложение о событиях в механизме сборки мусора, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4acf5-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="4acf5-104">Участники</span><span class="sxs-lookup"><span data-stu-id="4acf5-104">Members</span></span>  
  
|<span data-ttu-id="4acf5-105">Член</span><span class="sxs-lookup"><span data-stu-id="4acf5-105">Member</span></span>|<span data-ttu-id="4acf5-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="4acf5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4acf5-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="4acf5-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="4acf5-108">Уведомляет узел, что среда CLR возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4acf5-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="4acf5-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="4acf5-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="4acf5-110">Уведомляет узел, что среда CLR приостановила выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4acf5-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="4acf5-111">Метод ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="4acf5-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="4acf5-112">Уведомляет хост, что поток, из которого был выполнен вызов метода готов заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4acf5-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4acf5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4acf5-113">Requirements</span></span>  
 <span data-ttu-id="4acf5-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4acf5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4acf5-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4acf5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4acf5-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4acf5-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4acf5-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4acf5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4acf5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4acf5-118">See Also</span></span>  
 [<span data-ttu-id="4acf5-119">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4acf5-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="4acf5-120">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4acf5-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="4acf5-121">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="4acf5-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="4acf5-122">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4acf5-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="4acf5-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4acf5-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
