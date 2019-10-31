---
title: Интерфейс IHostCrst
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130527"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="c113f-102">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="c113f-102">IHostCrst Interface</span></span>
<span data-ttu-id="c113f-103">Служит в качестве представления критической секции для потоков в основном приложении.</span><span class="sxs-lookup"><span data-stu-id="c113f-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c113f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c113f-104">Methods</span></span>  
  
|<span data-ttu-id="c113f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c113f-105">Method</span></span>|<span data-ttu-id="c113f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c113f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c113f-107">Метод Enter</span><span class="sxs-lookup"><span data-stu-id="c113f-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="c113f-108">Входит в критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="c113f-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="c113f-109">Метод Leave</span><span class="sxs-lookup"><span data-stu-id="c113f-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="c113f-110">Оставляет критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="c113f-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="c113f-111">Метод SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="c113f-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="c113f-112">Задает счетчик счетчиков для критической секции.</span><span class="sxs-lookup"><span data-stu-id="c113f-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="c113f-113">Метод TryEnter</span><span class="sxs-lookup"><span data-stu-id="c113f-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="c113f-114">Пытается войти в критическую секцию и немедленно сообщает об успешном или неуспешном завершении.</span><span class="sxs-lookup"><span data-stu-id="c113f-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c113f-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="c113f-115">Remarks</span></span>  
 <span data-ttu-id="c113f-116">`IHostCrst` позволяет среде CLR взаимодействовать непосредственно с представлением критического раздела в основном приложении вместо использования функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="c113f-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c113f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c113f-117">Requirements</span></span>  
 <span data-ttu-id="c113f-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c113f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c113f-119">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c113f-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c113f-120">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c113f-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c113f-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c113f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c113f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c113f-122">See also</span></span>

- [<span data-ttu-id="c113f-123">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="c113f-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c113f-124">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="c113f-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="c113f-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c113f-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
