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
ms.openlocfilehash: 1d3f588bfc9799ed4591114b28d081ab417678b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914799"
---
# <a name="igchost-interface"></a><span data-ttu-id="4a7d0-102">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="4a7d0-102">IGCHost Interface</span></span>
<span data-ttu-id="4a7d0-103">Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a7d0-104">Начиная с .NET Framework 4,5, можно использовать метод [IGCHost2:: SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) , чтобы задать размер сегмента сборки мусора и максимальный размер поколения 0 системы сборки мусора в значениях, `DWORD` превышающих ограничение, которое накладывается методом [сетгкстартуплимитс](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4a7d0-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a7d0-105">Этот интерфейс предназначен только для экспертного использования.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-105">This interface is for expert usage only.</span></span> <span data-ttu-id="4a7d0-106">Это может повлиять на производительность приложения при неправильном использовании.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a7d0-107">Методы</span><span class="sxs-lookup"><span data-stu-id="4a7d0-107">Methods</span></span>  
  
|<span data-ttu-id="4a7d0-108">Метод</span><span class="sxs-lookup"><span data-stu-id="4a7d0-108">Method</span></span>|<span data-ttu-id="4a7d0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4a7d0-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a7d0-110">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="4a7d0-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="4a7d0-111">Принудительно выполняет сбор данных для данного поколения независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="4a7d0-112">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="4a7d0-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="4a7d0-113">Возвращает статистику текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="4a7d0-114">Метод GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="4a7d0-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="4a7d0-115">Возвращает статистику по потокам для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="4a7d0-116">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="4a7d0-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="4a7d0-117">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="4a7d0-118">Метод SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="4a7d0-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="4a7d0-119">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a7d0-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a7d0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="4a7d0-120">Requirements</span></span>  
 <span data-ttu-id="4a7d0-121">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a7d0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a7d0-122">**Заголовок.** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="4a7d0-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4a7d0-123">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a7d0-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a7d0-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a7d0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7d0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4a7d0-125">See also</span></span>

- [<span data-ttu-id="4a7d0-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4a7d0-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4a7d0-127">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4a7d0-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
