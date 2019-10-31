---
title: Интерфейс IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 43c16415c91521194e0d88be84dd176c3fdadad1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134835"
---
# <a name="igchost2-interface"></a><span data-ttu-id="e592c-102">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="e592c-102">IGCHost2 Interface</span></span>
<span data-ttu-id="e592c-103">Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="e592c-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e592c-104">Для новой разработки рекомендуется вместо этого использовать интерфейс [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e592c-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e592c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e592c-105">Methods</span></span>  
  
|<span data-ttu-id="e592c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e592c-106">Method</span></span>|<span data-ttu-id="e592c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e592c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e592c-108">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="e592c-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="e592c-109">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="e592c-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="e592c-110">Включает поколение 0 и размеры сегментов, превышающие `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="e592c-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e592c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e592c-111">Requirements</span></span>  
 <span data-ttu-id="e592c-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e592c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e592c-113">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="e592c-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e592c-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e592c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e592c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e592c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e592c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e592c-116">See also</span></span>

- [<span data-ttu-id="e592c-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e592c-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e592c-118">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e592c-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="e592c-119">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e592c-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
