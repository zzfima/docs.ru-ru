---
title: "Интерфейс IHostManualEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d55500efbe808b2fce16e869422e727b8ed0b93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="e0d11-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="e0d11-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="e0d11-103">Предоставляет реализацию узла представления событие ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="e0d11-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0d11-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e0d11-104">Methods</span></span>  
  
|<span data-ttu-id="e0d11-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e0d11-105">Method</span></span>|<span data-ttu-id="e0d11-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="e0d11-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0d11-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="e0d11-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="e0d11-108">Сбрасывает текущий `IHostManualEvent` несигнальное состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e0d11-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="e0d11-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="e0d11-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="e0d11-110">Задает текущий `IHostManualEvent` экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="e0d11-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="e0d11-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="e0d11-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="e0d11-112">Вызывает текущий `IHostManualEvent` экземпляр ожидать его признания или определенного времени.</span><span class="sxs-lookup"><span data-stu-id="e0d11-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0d11-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e0d11-113">Requirements</span></span>  
 <span data-ttu-id="e0d11-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0d11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0d11-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0d11-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0d11-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0d11-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0d11-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0d11-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d11-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e0d11-118">See Also</span></span>  
 [<span data-ttu-id="e0d11-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e0d11-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e0d11-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="e0d11-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="e0d11-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="e0d11-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="e0d11-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e0d11-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="e0d11-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e0d11-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
