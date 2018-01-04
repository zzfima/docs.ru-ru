---
title: "Интерфейс ICLRGCManager2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a8b51cf4297c1ccadbef8730c06148263d310e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="a0066-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="a0066-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="a0066-103">Предоставляет методы, позволяющие ведущему приложению взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a0066-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0066-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0066-104">Methods</span></span>  
  
|<span data-ttu-id="a0066-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0066-105">Method</span></span>|<span data-ttu-id="a0066-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="a0066-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0066-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="a0066-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="a0066-108">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="a0066-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="a0066-109">Позволяет поколения 0 и больше размера сегментов `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="a0066-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0066-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0066-110">Remarks</span></span>  
 <span data-ttu-id="a0066-111">Этот интерфейс наследует от [iclrgcmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a0066-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="a0066-112">Общеязыковая среда выполнения (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="a0066-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="a0066-113">Дополнительные сведения о системе сборки мусора см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="a0066-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0066-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a0066-114">Requirements</span></span>  
 <span data-ttu-id="a0066-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0066-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0066-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0066-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0066-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0066-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0066-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0066-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0066-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a0066-119">See Also</span></span>  
 [<span data-ttu-id="a0066-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="a0066-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="a0066-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="a0066-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="a0066-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a0066-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a0066-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="a0066-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="a0066-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a0066-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a0066-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="a0066-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
