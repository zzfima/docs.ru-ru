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
ms.openlocfilehash: 0927b236af094b964261a9b2a49a33d1ea2b9391
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="da3be-102">Интерфейс IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="da3be-102">IHostGCManager Interface</span></span>
<span data-ttu-id="da3be-103">Предоставляет методы, уведомляющие основное приложение о событиях в механизме сборки мусора, реализуемый общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="da3be-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="da3be-104">Члены</span><span class="sxs-lookup"><span data-stu-id="da3be-104">Members</span></span>  
  
|<span data-ttu-id="da3be-105">Член</span><span class="sxs-lookup"><span data-stu-id="da3be-105">Member</span></span>|<span data-ttu-id="da3be-106">Описание</span><span class="sxs-lookup"><span data-stu-id="da3be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da3be-107">Метод SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="da3be-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="da3be-108">Уведомляет узел, что среда CLR возобновляет выполнение задачи в потоках, которые были приостановлены для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="da3be-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="da3be-109">Метод SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="da3be-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="da3be-110">Уведомляет узел, что среда CLR приостановила выполнение задачи для выполнения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="da3be-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="da3be-111">Threadisblockingforsuspension-метод</span><span class="sxs-lookup"><span data-stu-id="da3be-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="da3be-112">Уведомляет хост, что поток, из которого был выполнен вызов метода готов заблокировать для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="da3be-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da3be-113">Требования</span><span class="sxs-lookup"><span data-stu-id="da3be-113">Requirements</span></span>  
 <span data-ttu-id="da3be-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da3be-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da3be-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da3be-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da3be-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da3be-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da3be-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da3be-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3be-118">См. также</span><span class="sxs-lookup"><span data-stu-id="da3be-118">See Also</span></span>  
 [<span data-ttu-id="da3be-119">ICLRTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="da3be-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="da3be-120">ICLRTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="da3be-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="da3be-121">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="da3be-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="da3be-122">IHostTaskManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="da3be-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="da3be-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="da3be-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
