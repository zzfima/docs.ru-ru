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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb5fea403f8210ea93d240aa3aabd4325524b987
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080947"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="08c53-102">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="08c53-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="08c53-103">Предоставляет представление реализации события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="08c53-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08c53-104">Методы</span><span class="sxs-lookup"><span data-stu-id="08c53-104">Methods</span></span>  
  
|<span data-ttu-id="08c53-105">Метод</span><span class="sxs-lookup"><span data-stu-id="08c53-105">Method</span></span>|<span data-ttu-id="08c53-106">Описание</span><span class="sxs-lookup"><span data-stu-id="08c53-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08c53-107">Метод Set</span><span class="sxs-lookup"><span data-stu-id="08c53-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="08c53-108">Задает текущий `IHostAutoEvent` экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="08c53-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="08c53-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="08c53-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="08c53-110">Вызывает текущий `IHostAutoEvent` экземпляр ожидать событие принадлежит или определенный промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="08c53-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08c53-111">Требования</span><span class="sxs-lookup"><span data-stu-id="08c53-111">Requirements</span></span>  
 <span data-ttu-id="08c53-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c53-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c53-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08c53-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08c53-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08c53-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="08c53-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08c53-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08c53-116">См. также</span><span class="sxs-lookup"><span data-stu-id="08c53-116">See also</span></span>

- [<span data-ttu-id="08c53-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="08c53-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="08c53-118">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="08c53-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="08c53-119">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="08c53-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="08c53-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="08c53-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
