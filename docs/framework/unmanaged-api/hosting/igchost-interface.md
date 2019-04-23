---
title: Интерфейс IGCHost
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228177"
---
# <a name="igchost-interface"></a><span data-ttu-id="062e4-102">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="062e4-102">IGCHost Interface</span></span>
<span data-ttu-id="062e4-103">Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="062e4-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="062e4-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 для значений больше, чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="062e4-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="062e4-105">Этот интерфейс является только для специалистов.</span><span class="sxs-lookup"><span data-stu-id="062e4-105">This interface is for expert usage only.</span></span> <span data-ttu-id="062e4-106">При неправильном, он может повлиять на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="062e4-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="062e4-107">Методы</span><span class="sxs-lookup"><span data-stu-id="062e4-107">Methods</span></span>  
  
|<span data-ttu-id="062e4-108">Метод</span><span class="sxs-lookup"><span data-stu-id="062e4-108">Method</span></span>|<span data-ttu-id="062e4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="062e4-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="062e4-110">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="062e4-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="062e4-111">Принудительное выполнения сборки для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="062e4-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="062e4-112">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="062e4-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="062e4-113">Получает статистику для текущего состояния сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="062e4-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="062e4-114">Метод GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="062e4-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="062e4-115">Получает статистику по потокам для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="062e4-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="062e4-116">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="062e4-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="062e4-117">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="062e4-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="062e4-118">Метод SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="062e4-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="062e4-119">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="062e4-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="062e4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="062e4-120">Requirements</span></span>  
 <span data-ttu-id="062e4-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="062e4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="062e4-122">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="062e4-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="062e4-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="062e4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="062e4-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="062e4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062e4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="062e4-125">See also</span></span>

- [<span data-ttu-id="062e4-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="062e4-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="062e4-127">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="062e4-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
