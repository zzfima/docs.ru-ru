---
title: Интерфейс IHostSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182290"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="dce36-102">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="dce36-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="dce36-103">Представляет реализация семафора для управления потоками.</span><span class="sxs-lookup"><span data-stu-id="dce36-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dce36-104">Методы</span><span class="sxs-lookup"><span data-stu-id="dce36-104">Methods</span></span>  
  
|<span data-ttu-id="dce36-105">Метод</span><span class="sxs-lookup"><span data-stu-id="dce36-105">Method</span></span>|<span data-ttu-id="dce36-106">Описание</span><span class="sxs-lookup"><span data-stu-id="dce36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dce36-107">Метод ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="dce36-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="dce36-108">Увеличивает счетчик текущего `IHostSemaphore` экземпляр на указанную величину.</span><span class="sxs-lookup"><span data-stu-id="dce36-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="dce36-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="dce36-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="dce36-110">Вызывает текущий `IHostSemaphore` экземпляр ждать, пока он принадлежал или заданного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="dce36-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dce36-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dce36-111">Requirements</span></span>  
 <span data-ttu-id="dce36-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce36-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce36-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dce36-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dce36-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dce36-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dce36-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dce36-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dce36-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dce36-116">See also</span></span>

- [<span data-ttu-id="dce36-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="dce36-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dce36-118">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="dce36-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="dce36-119">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="dce36-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="dce36-120">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dce36-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="dce36-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="dce36-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
