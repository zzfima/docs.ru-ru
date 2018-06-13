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
ms.openlocfilehash: 53aaf4c23861666962e5567a6cf9eb9fffc6292f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438760"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="e0394-102">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="e0394-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="e0394-103">Предоставляет реализацию узла представления событие ручного сброса.</span><span class="sxs-lookup"><span data-stu-id="e0394-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0394-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e0394-104">Methods</span></span>  
  
|<span data-ttu-id="e0394-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e0394-105">Method</span></span>|<span data-ttu-id="e0394-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e0394-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0394-107">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="e0394-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="e0394-108">Сбрасывает текущий `IHostManualEvent` несигнальное состояние экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e0394-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="e0394-109">Метод Set</span><span class="sxs-lookup"><span data-stu-id="e0394-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="e0394-110">Задает текущий `IHostManualEvent` экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="e0394-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="e0394-111">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="e0394-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="e0394-112">Вызывает текущий `IHostManualEvent` экземпляр ожидать его признания или определенного времени.</span><span class="sxs-lookup"><span data-stu-id="e0394-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0394-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e0394-113">Requirements</span></span>  
 <span data-ttu-id="e0394-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0394-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0394-115">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0394-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0394-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0394-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0394-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0394-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0394-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e0394-118">See Also</span></span>  
 [<span data-ttu-id="e0394-119">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e0394-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e0394-120">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="e0394-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="e0394-121">Интерфейс IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="e0394-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="e0394-122">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e0394-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="e0394-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e0394-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
