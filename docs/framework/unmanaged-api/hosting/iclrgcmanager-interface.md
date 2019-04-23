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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152169"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="abf42-102">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="abf42-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="abf42-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="abf42-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abf42-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 для значения больше чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="abf42-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="abf42-105">Методы</span><span class="sxs-lookup"><span data-stu-id="abf42-105">Methods</span></span>  
  
|<span data-ttu-id="abf42-106">Метод</span><span class="sxs-lookup"><span data-stu-id="abf42-106">Method</span></span>|<span data-ttu-id="abf42-107">Описание</span><span class="sxs-lookup"><span data-stu-id="abf42-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="abf42-108">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="abf42-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="abf42-109">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="abf42-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="abf42-110">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="abf42-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="abf42-111">Получает набор текущую статистику о сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="abf42-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="abf42-112">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="abf42-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="abf42-113">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="abf42-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abf42-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="abf42-114">Remarks</span></span>  
 <span data-ttu-id="abf42-115">Среда CLR (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="abf42-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="abf42-116">Дополнительные сведения о сборщик мусора, см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="abf42-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf42-117">Требования</span><span class="sxs-lookup"><span data-stu-id="abf42-117">Requirements</span></span>  
 <span data-ttu-id="abf42-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf42-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf42-119">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abf42-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abf42-120">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abf42-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abf42-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf42-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf42-122">См. также</span><span class="sxs-lookup"><span data-stu-id="abf42-122">See also</span></span>

- [<span data-ttu-id="abf42-123">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="abf42-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="abf42-124">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="abf42-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="abf42-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="abf42-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="abf42-126">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="abf42-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="abf42-127">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="abf42-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="abf42-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="abf42-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
