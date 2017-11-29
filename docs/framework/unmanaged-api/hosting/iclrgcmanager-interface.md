---
title: "Интерфейс ICLRGCManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager
helpviewer_keywords: ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7215ce1423e8541b23daae7b9e051ade6e25f1b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="252fe-102">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="252fe-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="252fe-103">Предоставляет методы, позволяющие ведущему приложению взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="252fe-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="252fe-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="252fe-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="252fe-105">Методы</span><span class="sxs-lookup"><span data-stu-id="252fe-105">Methods</span></span>  
  
|<span data-ttu-id="252fe-106">Метод</span><span class="sxs-lookup"><span data-stu-id="252fe-106">Method</span></span>|<span data-ttu-id="252fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="252fe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="252fe-108">Collect-метод</span><span class="sxs-lookup"><span data-stu-id="252fe-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="252fe-109">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="252fe-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="252fe-110">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="252fe-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="252fe-111">Получает набор текущих статистических данных о системе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="252fe-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="252fe-112">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="252fe-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="252fe-113">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="252fe-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="252fe-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="252fe-114">Remarks</span></span>  
 <span data-ttu-id="252fe-115">Общеязыковая среда выполнения (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="252fe-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="252fe-116">Дополнительные сведения о системе сборки мусора см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="252fe-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="252fe-117">Требования</span><span class="sxs-lookup"><span data-stu-id="252fe-117">Requirements</span></span>  
 <span data-ttu-id="252fe-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="252fe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="252fe-119">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="252fe-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="252fe-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="252fe-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="252fe-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="252fe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="252fe-122">См. также</span><span class="sxs-lookup"><span data-stu-id="252fe-122">See Also</span></span>  
 [<span data-ttu-id="252fe-123">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="252fe-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="252fe-124">COR_GC_STATS-структура</span><span class="sxs-lookup"><span data-stu-id="252fe-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="252fe-125">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="252fe-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="252fe-126">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="252fe-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="252fe-127">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="252fe-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="252fe-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="252fe-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
