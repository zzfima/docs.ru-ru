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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599459"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="a02f1-102">Интерфейс IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a02f1-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="a02f1-103">Предоставляет представление реализации события автоматического сброса.</span><span class="sxs-lookup"><span data-stu-id="a02f1-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a02f1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a02f1-104">Methods</span></span>  
  
|<span data-ttu-id="a02f1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a02f1-105">Method</span></span>|<span data-ttu-id="a02f1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a02f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a02f1-107">Метод Set</span><span class="sxs-lookup"><span data-stu-id="a02f1-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="a02f1-108">Задает текущий `IHostAutoEvent` экземпляр сигнальное состояние.</span><span class="sxs-lookup"><span data-stu-id="a02f1-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a02f1-109">Метод Wait</span><span class="sxs-lookup"><span data-stu-id="a02f1-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="a02f1-110">Вызывает текущий `IHostAutoEvent` экземпляр ожидать событие принадлежит или определенный промежуток времени.</span><span class="sxs-lookup"><span data-stu-id="a02f1-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a02f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a02f1-111">Requirements</span></span>  
 <span data-ttu-id="a02f1-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a02f1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a02f1-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a02f1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a02f1-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a02f1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a02f1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a02f1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a02f1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a02f1-116">See also</span></span>

- [<span data-ttu-id="a02f1-117">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a02f1-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a02f1-118">Интерфейс IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="a02f1-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="a02f1-119">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a02f1-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="a02f1-120">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a02f1-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
