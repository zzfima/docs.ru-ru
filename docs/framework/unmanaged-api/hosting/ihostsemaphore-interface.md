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
ms.openlocfilehash: 2cf490bcd167b7a498ae21f479f616694ccb5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139479"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="cf1ae-102">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="cf1ae-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="cf1ae-103">Представляет реализацию семафора для потоков в ведущем приложении.</span><span class="sxs-lookup"><span data-stu-id="cf1ae-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf1ae-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cf1ae-104">Methods</span></span>  
  
|<span data-ttu-id="cf1ae-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cf1ae-105">Method</span></span>|<span data-ttu-id="cf1ae-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cf1ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf1ae-107">Метод ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="cf1ae-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="cf1ae-108">Увеличивает количество текущего экземпляра `IHostSemaphore` на указанный объем.</span><span class="sxs-lookup"><span data-stu-id="cf1ae-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="cf1ae-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="cf1ae-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="cf1ae-110">Приводит к тому, что текущий экземпляр `IHostSemaphore` ожидает его признания или истечения указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="cf1ae-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf1ae-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cf1ae-111">Requirements</span></span>  
 <span data-ttu-id="cf1ae-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf1ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf1ae-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf1ae-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf1ae-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf1ae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf1ae-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf1ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cf1ae-116">See also</span></span>

- [<span data-ttu-id="cf1ae-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="cf1ae-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="cf1ae-118">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="cf1ae-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="cf1ae-119">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="cf1ae-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="cf1ae-120">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="cf1ae-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="cf1ae-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cf1ae-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
