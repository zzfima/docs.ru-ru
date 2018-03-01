---
title: "Интерфейс IHostCrst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a9ed2b390ad741d90f9179ef5101d328d3b639d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="caa0c-102">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="caa0c-102">IHostCrst Interface</span></span>
<span data-ttu-id="caa0c-103">Служит в качестве узла представления критической секции для работы с потоками.</span><span class="sxs-lookup"><span data-stu-id="caa0c-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caa0c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="caa0c-104">Methods</span></span>  
  
|<span data-ttu-id="caa0c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="caa0c-105">Method</span></span>|<span data-ttu-id="caa0c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="caa0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caa0c-107">Метод Enter</span><span class="sxs-lookup"><span data-stu-id="caa0c-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="caa0c-108">Переходит в критической секции.</span><span class="sxs-lookup"><span data-stu-id="caa0c-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="caa0c-109">Метод Leave</span><span class="sxs-lookup"><span data-stu-id="caa0c-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="caa0c-110">Покидает критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="caa0c-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="caa0c-111">Метод SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="caa0c-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="caa0c-112">Задает счетчик прокруток для критической секции.</span><span class="sxs-lookup"><span data-stu-id="caa0c-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="caa0c-113">Метод TryEnter</span><span class="sxs-lookup"><span data-stu-id="caa0c-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="caa0c-114">Пытается ввести критическую секцию и сообщает об успехе или сбоя немедленно.</span><span class="sxs-lookup"><span data-stu-id="caa0c-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caa0c-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="caa0c-115">Remarks</span></span>  
 <span data-ttu-id="caa0c-116">`IHostCrst`позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением узла критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="caa0c-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa0c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="caa0c-117">Requirements</span></span>  
 <span data-ttu-id="caa0c-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa0c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa0c-119">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="caa0c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="caa0c-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caa0c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caa0c-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa0c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa0c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="caa0c-122">See Also</span></span>  
 [<span data-ttu-id="caa0c-123">Интерфейс ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="caa0c-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="caa0c-124">Интерфейс IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="caa0c-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="caa0c-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="caa0c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
