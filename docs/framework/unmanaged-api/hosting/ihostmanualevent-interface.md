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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad580f7cab81323e09a24dc12db39f223be3aeb4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973073"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="89218-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="89218-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="89218-103">Предоставляет реализацию главного приложения является представлением событие со сбросом вручную.</span><span class="sxs-lookup"><span data-stu-id="89218-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89218-104">Методы</span><span class="sxs-lookup"><span data-stu-id="89218-104">Methods</span></span>  
  
|<span data-ttu-id="89218-105">Метод</span><span class="sxs-lookup"><span data-stu-id="89218-105">Method</span></span>|<span data-ttu-id="89218-106">Описание</span><span class="sxs-lookup"><span data-stu-id="89218-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89218-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="89218-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="89218-108">Сбрасывает текущий `IHostManualEvent` экземпляра в сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="89218-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="89218-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="89218-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="89218-110">Задает текущий `IHostManualEvent` экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="89218-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="89218-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="89218-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="89218-112">Вызывает текущий `IHostManualEvent` экземпляр ждать, пока он принадлежал или определенный промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="89218-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89218-113">Требования</span><span class="sxs-lookup"><span data-stu-id="89218-113">Requirements</span></span>  
 <span data-ttu-id="89218-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89218-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89218-115">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="89218-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89218-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89218-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89218-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89218-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89218-118">См. также</span><span class="sxs-lookup"><span data-stu-id="89218-118">See also</span></span>

- [<span data-ttu-id="89218-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="89218-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="89218-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="89218-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="89218-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="89218-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="89218-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="89218-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="89218-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="89218-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
