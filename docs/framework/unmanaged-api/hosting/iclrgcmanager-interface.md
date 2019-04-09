---
title: Интерфейс ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152169"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="de7b0-102">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="de7b0-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="de7b0-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="de7b0-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de7b0-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 для значения больше чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="de7b0-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de7b0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="de7b0-105">Methods</span></span>  
  
|<span data-ttu-id="de7b0-106">Метод</span><span class="sxs-lookup"><span data-stu-id="de7b0-106">Method</span></span>|<span data-ttu-id="de7b0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="de7b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de7b0-108">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="de7b0-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="de7b0-109">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="de7b0-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="de7b0-110">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="de7b0-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="de7b0-111">Получает набор текущую статистику о сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="de7b0-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="de7b0-112">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="de7b0-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="de7b0-113">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="de7b0-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de7b0-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="de7b0-114">Remarks</span></span>  
 <span data-ttu-id="de7b0-115">Среда CLR (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="de7b0-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="de7b0-116">Дополнительные сведения о сборщик мусора, см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="de7b0-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de7b0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="de7b0-117">Requirements</span></span>  
 <span data-ttu-id="de7b0-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de7b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de7b0-119">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de7b0-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de7b0-120">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de7b0-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="de7b0-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="de7b0-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de7b0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="de7b0-122">See also</span></span>

- [<span data-ttu-id="de7b0-123">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="de7b0-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="de7b0-124">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="de7b0-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="de7b0-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="de7b0-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="de7b0-126">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="de7b0-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="de7b0-127">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="de7b0-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="de7b0-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="de7b0-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
