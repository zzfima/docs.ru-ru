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
ms.openlocfilehash: b025ec31e3797fec3ac184929f1274cb5f68501b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="970d5-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="970d5-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="970d5-103">Предоставляет методы, позволяющие ведущему приложению взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="970d5-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="970d5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="970d5-104">Methods</span></span>  
  
|<span data-ttu-id="970d5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="970d5-105">Method</span></span>|<span data-ttu-id="970d5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="970d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="970d5-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="970d5-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="970d5-108">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="970d5-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="970d5-109">Позволяет поколения 0 и больше размера сегментов `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="970d5-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="970d5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="970d5-110">Remarks</span></span>  
 <span data-ttu-id="970d5-111">Этот интерфейс наследует от [iclrgcmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="970d5-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="970d5-112">Общеязыковая среда выполнения (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="970d5-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="970d5-113">Дополнительные сведения о системе сборки мусора см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="970d5-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970d5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="970d5-114">Requirements</span></span>  
 <span data-ttu-id="970d5-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="970d5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="970d5-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="970d5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="970d5-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="970d5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="970d5-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="970d5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970d5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="970d5-119">See Also</span></span>  
 [<span data-ttu-id="970d5-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="970d5-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="970d5-121">COR_GC_STATS-структура</span><span class="sxs-lookup"><span data-stu-id="970d5-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="970d5-122">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="970d5-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="970d5-123">Интерфейсы размещения CLR, добавленные в .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="970d5-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="970d5-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="970d5-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="970d5-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="970d5-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
