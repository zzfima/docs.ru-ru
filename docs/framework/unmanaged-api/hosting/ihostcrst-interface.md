---
title: "Интерфейс IHostCrst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="98f74-102">Интерфейс IHostCrst</span><span class="sxs-lookup"><span data-stu-id="98f74-102">IHostCrst Interface</span></span>
<span data-ttu-id="98f74-103">Служит в качестве узла представления критической секции для работы с потоками.</span><span class="sxs-lookup"><span data-stu-id="98f74-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98f74-104">Методы</span><span class="sxs-lookup"><span data-stu-id="98f74-104">Methods</span></span>  
  
|<span data-ttu-id="98f74-105">Метод</span><span class="sxs-lookup"><span data-stu-id="98f74-105">Method</span></span>|<span data-ttu-id="98f74-106">Описание</span><span class="sxs-lookup"><span data-stu-id="98f74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98f74-107">ENTER-метод</span><span class="sxs-lookup"><span data-stu-id="98f74-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="98f74-108">Переходит в критической секции.</span><span class="sxs-lookup"><span data-stu-id="98f74-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="98f74-109">Leave-метод</span><span class="sxs-lookup"><span data-stu-id="98f74-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="98f74-110">Покидает критическую секцию.</span><span class="sxs-lookup"><span data-stu-id="98f74-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="98f74-111">Setspincount-метод</span><span class="sxs-lookup"><span data-stu-id="98f74-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="98f74-112">Задает счетчик прокруток для критической секции.</span><span class="sxs-lookup"><span data-stu-id="98f74-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="98f74-113">TryEnter-метод</span><span class="sxs-lookup"><span data-stu-id="98f74-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="98f74-114">Пытается ввести критическую секцию и сообщает об успехе или сбоя немедленно.</span><span class="sxs-lookup"><span data-stu-id="98f74-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98f74-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="98f74-115">Remarks</span></span>  
 <span data-ttu-id="98f74-116">`IHostCrst`позволяет общеязыковой среды выполнения (CLR) для взаимодействия непосредственно с представлением узла критическую секцию, а не с помощью функций Win32, таких как `EnterCriticalSection` или `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="98f74-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f74-117">Требования</span><span class="sxs-lookup"><span data-stu-id="98f74-117">Requirements</span></span>  
 <span data-ttu-id="98f74-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98f74-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98f74-119">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98f74-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98f74-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98f74-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98f74-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98f74-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f74-122">См. также</span><span class="sxs-lookup"><span data-stu-id="98f74-122">See Also</span></span>  
 [<span data-ttu-id="98f74-123">ICLRSyncManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="98f74-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="98f74-124">Ihostsyncmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="98f74-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="98f74-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="98f74-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
