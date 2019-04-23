---
title: Интерфейс ICLRMemoryNotificationCallback
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212158"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="1d7ab-102">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="1d7ab-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="1d7ab-103">Позволяет узлу отчетов об условиях нехватки памяти с помощью подхода, аналогичную Win32 `CreateMemoryResourceNotification` функции.</span><span class="sxs-lookup"><span data-stu-id="1d7ab-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d7ab-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1d7ab-104">Methods</span></span>  
  
|<span data-ttu-id="1d7ab-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1d7ab-105">Method</span></span>|<span data-ttu-id="1d7ab-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1d7ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d7ab-107">Метод OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="1d7ab-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="1d7ab-108">Уведомляет общеязыковой среды выполнения (CLR) загрузки памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d7ab-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d7ab-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d7ab-109">Remarks</span></span>  
 <span data-ttu-id="1d7ab-110">На узле используется `ICLRMemoryNotificationCallback` интерфейс для запроса, что среда CLR освободить ресурсы памяти.</span><span class="sxs-lookup"><span data-stu-id="1d7ab-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d7ab-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1d7ab-111">Requirements</span></span>  
 <span data-ttu-id="1d7ab-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7ab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7ab-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d7ab-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d7ab-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d7ab-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d7ab-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7ab-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1d7ab-116">See also</span></span>

- [<span data-ttu-id="1d7ab-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="1d7ab-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="1d7ab-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1d7ab-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
