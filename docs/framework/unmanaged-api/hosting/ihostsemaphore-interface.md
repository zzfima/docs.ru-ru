---
title: "Интерфейс IHostSemaphore"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore
helpviewer_keywords: IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67b3225186f74fceadfb3104145743823ef82fc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="1ede7-102">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="1ede7-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="1ede7-103">Представляет реализацию поставщика услуг размещения семафор для работы с потоками.</span><span class="sxs-lookup"><span data-stu-id="1ede7-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ede7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1ede7-104">Methods</span></span>  
  
|<span data-ttu-id="1ede7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1ede7-105">Method</span></span>|<span data-ttu-id="1ede7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1ede7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ede7-107">ReleaseSemaphore-метод</span><span class="sxs-lookup"><span data-stu-id="1ede7-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="1ede7-108">Увеличивает счетчик текущего `IHostSemaphore` экземпляр на указанную величину.</span><span class="sxs-lookup"><span data-stu-id="1ede7-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="1ede7-109">Wait-метод</span><span class="sxs-lookup"><span data-stu-id="1ede7-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="1ede7-110">Вызывает текущий `IHostSemaphore` экземпляр ожидать его признания или указанного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="1ede7-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ede7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1ede7-111">Requirements</span></span>  
 <span data-ttu-id="1ede7-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ede7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ede7-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ede7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ede7-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ede7-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ede7-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ede7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ede7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1ede7-116">See Also</span></span>  
 [<span data-ttu-id="1ede7-117">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1ede7-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1ede7-118">IHostAutoEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1ede7-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="1ede7-119">IHostManualEvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1ede7-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1ede7-120">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1ede7-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="1ede7-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1ede7-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
