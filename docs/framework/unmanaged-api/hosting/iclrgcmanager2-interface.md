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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700437"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="6adc6-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="6adc6-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="6adc6-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6adc6-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6adc6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6adc6-104">Methods</span></span>  
  
|<span data-ttu-id="6adc6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6adc6-105">Method</span></span>|<span data-ttu-id="6adc6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6adc6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6adc6-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="6adc6-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="6adc6-108">Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.</span><span class="sxs-lookup"><span data-stu-id="6adc6-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="6adc6-109">Позволяет поколения 0 и размера сегментов, размер которых превышает `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="6adc6-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6adc6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6adc6-110">Remarks</span></span>  
 <span data-ttu-id="6adc6-111">Этот интерфейс наследует от [интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6adc6-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="6adc6-112">Среда CLR (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа.</span><span class="sxs-lookup"><span data-stu-id="6adc6-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="6adc6-113">Дополнительные сведения о сборщик мусора, см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="6adc6-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6adc6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6adc6-114">Requirements</span></span>  
 <span data-ttu-id="6adc6-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6adc6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6adc6-116">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6adc6-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6adc6-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6adc6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6adc6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6adc6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adc6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6adc6-119">See also</span></span>

- [<span data-ttu-id="6adc6-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="6adc6-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="6adc6-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="6adc6-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="6adc6-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6adc6-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6adc6-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="6adc6-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="6adc6-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6adc6-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="6adc6-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="6adc6-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
