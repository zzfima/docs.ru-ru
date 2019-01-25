---
title: Интерфейс ICLRGCManager2
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897526882a8ae53410a7744f78c558dfa6981e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708588"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="95d82-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="95d82-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="95d82-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="95d82-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95d82-104">Методы</span><span class="sxs-lookup"><span data-stu-id="95d82-104">Methods</span></span>  
  
|<span data-ttu-id="95d82-105">Метод</span><span class="sxs-lookup"><span data-stu-id="95d82-105">Method</span></span>|<span data-ttu-id="95d82-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="95d82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95d82-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="95d82-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="95d82-108">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="95d82-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="95d82-109">Позволяет поколения 0 и размера сегментов, размер которых превышает `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="95d82-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95d82-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="95d82-110">Remarks</span></span>  
 <span data-ttu-id="95d82-111">Этот интерфейс наследует от [интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="95d82-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="95d82-112">Среда CLR (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="95d82-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="95d82-113">Дополнительные сведения о сборщик мусора, см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="95d82-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d82-114">Требования</span><span class="sxs-lookup"><span data-stu-id="95d82-114">Requirements</span></span>  
 <span data-ttu-id="95d82-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d82-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d82-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95d82-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95d82-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95d82-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95d82-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d82-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d82-119">См. также</span><span class="sxs-lookup"><span data-stu-id="95d82-119">See also</span></span>
- [<span data-ttu-id="95d82-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="95d82-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="95d82-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="95d82-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="95d82-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="95d82-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="95d82-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="95d82-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="95d82-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="95d82-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="95d82-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="95d82-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
