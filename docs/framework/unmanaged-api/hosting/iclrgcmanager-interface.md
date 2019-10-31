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
ms.openlocfilehash: 08c46ecbad85e3cc15f60d1cc8dae6b8281702ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141131"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="ec48b-102">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="ec48b-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="ec48b-103">Предоставляет методы, позволяющие узлу взаимодействовать с системой сборки мусора среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ec48b-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec48b-104">Начиная с .NET Framework 4,5, можно использовать метод [ICLRGCManager2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) , чтобы задать размер сегмента сборки мусора и максимальный размер поколения 0 системы сборки мусора в значениях, превышающих `DWORD` ограничение, которое накладывается методом [сетгкстартуплимитс](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec48b-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec48b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ec48b-105">Methods</span></span>  
  
|<span data-ttu-id="ec48b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ec48b-106">Method</span></span>|<span data-ttu-id="ec48b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ec48b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec48b-108">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="ec48b-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="ec48b-109">Вызывает принудительную сборку мусора для указанного поколения.</span><span class="sxs-lookup"><span data-stu-id="ec48b-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="ec48b-110">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="ec48b-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="ec48b-111">Возвращает набор текущих статистических данных о системе сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ec48b-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="ec48b-112">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="ec48b-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="ec48b-113">Задает размер сегмента сборки мусора и максимальный размер поколения 0 для системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ec48b-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec48b-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="ec48b-114">Remarks</span></span>  
 <span data-ttu-id="ec48b-115">Среда CLR реализует механизм сборки мусора с типом управляемого <xref:System.GC>.</span><span class="sxs-lookup"><span data-stu-id="ec48b-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="ec48b-116">Дополнительные сведения о системе сборки мусора см. в разделе [сборка мусора](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="ec48b-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec48b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="ec48b-117">Requirements</span></span>  
 <span data-ttu-id="ec48b-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec48b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec48b-119">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ec48b-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec48b-120">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec48b-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec48b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec48b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec48b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ec48b-122">See also</span></span>

- [<span data-ttu-id="ec48b-123">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="ec48b-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="ec48b-124">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="ec48b-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="ec48b-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ec48b-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ec48b-126">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ec48b-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="ec48b-127">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ec48b-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ec48b-128">Размещение</span><span class="sxs-lookup"><span data-stu-id="ec48b-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
