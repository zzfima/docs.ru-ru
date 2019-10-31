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
ms.openlocfilehash: 72ffd7b47795ee8e46f8fbff07559133843793e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141157"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="32aa3-102">Интерфейс ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="32aa3-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="32aa3-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="32aa3-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="32aa3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="32aa3-104">Methods</span></span>  
  
|<span data-ttu-id="32aa3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="32aa3-105">Method</span></span>|<span data-ttu-id="32aa3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="32aa3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="32aa3-107">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="32aa3-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="32aa3-108">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="32aa3-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="32aa3-109">Включает поколение 0 и размеры сегментов, превышающие `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="32aa3-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32aa3-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="32aa3-110">Remarks</span></span>  
 <span data-ttu-id="32aa3-111">Этот интерфейс наследуется от [интерфейса иклргкманажер](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="32aa3-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="32aa3-112">Среда CLR реализует механизм сборки мусора с типом управляемого <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="32aa3-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="32aa3-113">Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="32aa3-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32aa3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="32aa3-114">Requirements</span></span>  
 <span data-ttu-id="32aa3-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32aa3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32aa3-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="32aa3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32aa3-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="32aa3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32aa3-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32aa3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32aa3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="32aa3-119">See also</span></span>

- [<span data-ttu-id="32aa3-120">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="32aa3-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="32aa3-121">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="32aa3-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="32aa3-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="32aa3-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="32aa3-123">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="32aa3-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="32aa3-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="32aa3-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="32aa3-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="32aa3-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
