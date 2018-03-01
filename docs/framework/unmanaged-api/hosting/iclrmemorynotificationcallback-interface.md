---
title: "Интерфейс ICLRMemoryNotificationCallback"
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
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc09e3668dc814360de0256c2476ffa7b61462ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="1409e-102">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="1409e-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="1409e-103">Позволяет узлу отчетов об условиях нехватки памяти с помощью подход, аналогичный Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="1409e-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1409e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1409e-104">Methods</span></span>  
  
|<span data-ttu-id="1409e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1409e-105">Method</span></span>|<span data-ttu-id="1409e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="1409e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1409e-107">Метод OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="1409e-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="1409e-108">Уведомляет общеязыковой среды выполнения (CLR) загрузки памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1409e-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1409e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1409e-109">Remarks</span></span>  
 <span data-ttu-id="1409e-110">Узел использует `ICLRMemoryNotificationCallback` интерфейс для запроса, что среда CLR освободить ресурсы памяти.</span><span class="sxs-lookup"><span data-stu-id="1409e-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1409e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1409e-111">Requirements</span></span>  
 <span data-ttu-id="1409e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1409e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1409e-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1409e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1409e-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1409e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1409e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1409e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1409e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1409e-116">See Also</span></span>  
 [<span data-ttu-id="1409e-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="1409e-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="1409e-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1409e-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
