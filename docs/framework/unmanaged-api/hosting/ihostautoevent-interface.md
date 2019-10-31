---
title: Интерфейс IHostAutoEvent
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: 2b191243ea03adcfecaadbd3a5871e1773b28bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124454"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="3b6ae-102">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="3b6ae-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="3b6ae-103">Предоставляет представление реализации события автоматического сброса в узле.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b6ae-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3b6ae-104">Methods</span></span>  
  
|<span data-ttu-id="3b6ae-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3b6ae-105">Method</span></span>|<span data-ttu-id="3b6ae-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3b6ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b6ae-107">Метод Set</span><span class="sxs-lookup"><span data-stu-id="3b6ae-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="3b6ae-108">Задает для текущего экземпляра `IHostAutoEvent` сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="3b6ae-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="3b6ae-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="3b6ae-110">Вызывает ожидание текущего экземпляра `IHostAutoEvent` до тех пор, пока не будет присвоено событие или не истечет указанное количество времени.</span><span class="sxs-lookup"><span data-stu-id="3b6ae-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b6ae-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3b6ae-111">Requirements</span></span>  
 <span data-ttu-id="3b6ae-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b6ae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b6ae-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3b6ae-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b6ae-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3b6ae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b6ae-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b6ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b6ae-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3b6ae-116">See also</span></span>

- [<span data-ttu-id="3b6ae-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3b6ae-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="3b6ae-118">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="3b6ae-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="3b6ae-119">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3b6ae-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="3b6ae-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3b6ae-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
