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
ms.openlocfilehash: a89a7ef34418163d790fd055de681c1cdf989e57
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226928"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="fbeb0-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="fbeb0-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="fbeb0-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fbeb0-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbeb0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fbeb0-104">Methods</span></span>  
  
|<span data-ttu-id="fbeb0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fbeb0-105">Method</span></span>|<span data-ttu-id="fbeb0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fbeb0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbeb0-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="fbeb0-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="fbeb0-108">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="fbeb0-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="fbeb0-109">Позволяет поколения 0 и размера сегментов, размер которых превышает `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="fbeb0-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbeb0-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbeb0-110">Remarks</span></span>  
 <span data-ttu-id="fbeb0-111">Этот интерфейс наследует от [интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fbeb0-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="fbeb0-112">Среда CLR (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="fbeb0-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="fbeb0-113">Дополнительные сведения о сборщик мусора, см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="fbeb0-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbeb0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fbeb0-114">Requirements</span></span>  
 <span data-ttu-id="fbeb0-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbeb0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbeb0-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbeb0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbeb0-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbeb0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbeb0-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbeb0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbeb0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fbeb0-119">See also</span></span>

- [<span data-ttu-id="fbeb0-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="fbeb0-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="fbeb0-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="fbeb0-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="fbeb0-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fbeb0-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="fbeb0-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="fbeb0-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="fbeb0-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="fbeb0-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="fbeb0-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="fbeb0-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
