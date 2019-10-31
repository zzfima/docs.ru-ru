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
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141005"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="6b5e9-102">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="6b5e9-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="6b5e9-103">Позволяет основному приложению сообщать об условиях нехватки памяти с помощью подхода, аналогичного функции Win32 `CreateMemoryResourceNotification`.</span><span class="sxs-lookup"><span data-stu-id="6b5e9-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b5e9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6b5e9-104">Methods</span></span>  
  
|<span data-ttu-id="6b5e9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6b5e9-105">Method</span></span>|<span data-ttu-id="6b5e9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6b5e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b5e9-107">Метод OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="6b5e9-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="6b5e9-108">Уведомляет среду CLR о загрузке памяти на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6b5e9-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b5e9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6b5e9-109">Remarks</span></span>  
 <span data-ttu-id="6b5e9-110">Узел использует интерфейс `ICLRMemoryNotificationCallback`, чтобы запросить в CLR ресурсы свободной памяти.</span><span class="sxs-lookup"><span data-stu-id="6b5e9-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b5e9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6b5e9-111">Requirements</span></span>  
 <span data-ttu-id="6b5e9-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b5e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b5e9-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b5e9-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b5e9-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b5e9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b5e9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b5e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5e9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6b5e9-116">See also</span></span>

- [<span data-ttu-id="6b5e9-117">Интерфейс IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="6b5e9-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="6b5e9-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6b5e9-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
