---
title: Интерфейс IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136784"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="4a14f-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4a14f-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="4a14f-103">Предоставляет реализацию представления события ручного сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="4a14f-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a14f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4a14f-104">Methods</span></span>  
  
|<span data-ttu-id="4a14f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4a14f-105">Method</span></span>|<span data-ttu-id="4a14f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4a14f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a14f-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="4a14f-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="4a14f-108">Сбрасывает текущий экземпляр `IHostManualEvent` в несигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="4a14f-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="4a14f-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="4a14f-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="4a14f-110">Задает для текущего экземпляра `IHostManualEvent` сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="4a14f-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="4a14f-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="4a14f-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="4a14f-112">Вызывает ожидание текущего экземпляра `IHostManualEvent` до его признания или истечения указанного времени.</span><span class="sxs-lookup"><span data-stu-id="4a14f-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a14f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4a14f-113">Requirements</span></span>  
 <span data-ttu-id="4a14f-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a14f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a14f-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4a14f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a14f-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a14f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a14f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a14f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a14f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4a14f-118">See also</span></span>

- [<span data-ttu-id="4a14f-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4a14f-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4a14f-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4a14f-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="4a14f-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4a14f-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="4a14f-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4a14f-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="4a14f-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4a14f-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
