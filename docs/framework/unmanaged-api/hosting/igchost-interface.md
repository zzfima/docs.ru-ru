---
title: "Интерфейс IGCHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0f398c09569a855291a1565ce63b513161a803
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="igchost-interface"></a><span data-ttu-id="3599e-102">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="3599e-102">IGCHost Interface</span></span>
<span data-ttu-id="3599e-103">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="3599e-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3599e-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3599e-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3599e-105">Этот интерфейс не только для специалистов.</span><span class="sxs-lookup"><span data-stu-id="3599e-105">This interface is for expert usage only.</span></span> <span data-ttu-id="3599e-106">При неправильном, он может повлиять на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="3599e-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3599e-107">Методы</span><span class="sxs-lookup"><span data-stu-id="3599e-107">Methods</span></span>  
  
|<span data-ttu-id="3599e-108">Метод</span><span class="sxs-lookup"><span data-stu-id="3599e-108">Method</span></span>|<span data-ttu-id="3599e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3599e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3599e-110">Collect-метод</span><span class="sxs-lookup"><span data-stu-id="3599e-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="3599e-111">Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3599e-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="3599e-112">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="3599e-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="3599e-113">Получает статистику для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3599e-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="3599e-114">Getthreadstats-метод</span><span class="sxs-lookup"><span data-stu-id="3599e-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="3599e-115">Получает статистику отдельного потока для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3599e-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="3599e-116">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="3599e-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="3599e-117">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="3599e-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="3599e-118">Setvirtualmemlimit-метод</span><span class="sxs-lookup"><span data-stu-id="3599e-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="3599e-119">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="3599e-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3599e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="3599e-120">Requirements</span></span>  
 <span data-ttu-id="3599e-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3599e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3599e-122">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="3599e-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="3599e-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3599e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3599e-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3599e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3599e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3599e-125">See Also</span></span>  
 [<span data-ttu-id="3599e-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3599e-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3599e-127">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3599e-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
