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
ms.openlocfilehash: a77cd85c0fafd9994418693c8d3c4b148c34dbe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437668"
---
# <a name="igchost-interface"></a><span data-ttu-id="85a98-102">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="85a98-102">IGCHost Interface</span></span>
<span data-ttu-id="85a98-103">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="85a98-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85a98-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="85a98-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85a98-105">Этот интерфейс не только для специалистов.</span><span class="sxs-lookup"><span data-stu-id="85a98-105">This interface is for expert usage only.</span></span> <span data-ttu-id="85a98-106">При неправильном, он может повлиять на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="85a98-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85a98-107">Методы</span><span class="sxs-lookup"><span data-stu-id="85a98-107">Methods</span></span>  
  
|<span data-ttu-id="85a98-108">Метод</span><span class="sxs-lookup"><span data-stu-id="85a98-108">Method</span></span>|<span data-ttu-id="85a98-109">Описание</span><span class="sxs-lookup"><span data-stu-id="85a98-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85a98-110">Метод Collect</span><span class="sxs-lookup"><span data-stu-id="85a98-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="85a98-111">Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="85a98-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="85a98-112">Метод GetStats</span><span class="sxs-lookup"><span data-stu-id="85a98-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="85a98-113">Получает статистику для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="85a98-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="85a98-114">Метод GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="85a98-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="85a98-115">Получает статистику отдельного потока для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="85a98-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="85a98-116">Метод SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="85a98-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="85a98-117">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="85a98-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="85a98-118">Метод SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="85a98-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="85a98-119">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="85a98-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85a98-120">Требования</span><span class="sxs-lookup"><span data-stu-id="85a98-120">Requirements</span></span>  
 <span data-ttu-id="85a98-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85a98-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a98-122">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="85a98-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="85a98-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85a98-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85a98-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a98-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a98-125">См. также</span><span class="sxs-lookup"><span data-stu-id="85a98-125">See Also</span></span>  
 [<span data-ttu-id="85a98-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="85a98-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="85a98-127">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="85a98-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
