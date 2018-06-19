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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6cbf44bd02a45b9b99d2dad63fc5bd6219c4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437681"
---
# <a name="igchost2-interface"></a><span data-ttu-id="506a5-102">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="506a5-102">IGCHost2 Interface</span></span>
<span data-ttu-id="506a5-103">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="506a5-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="506a5-104">Для разработки новых приложений рекомендуется использовать [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="506a5-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="506a5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="506a5-105">Methods</span></span>  
  
|<span data-ttu-id="506a5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="506a5-106">Method</span></span>|<span data-ttu-id="506a5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="506a5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="506a5-108">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="506a5-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="506a5-109">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="506a5-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="506a5-110">Позволяет поколения 0 и больше размера сегментов `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="506a5-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="506a5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="506a5-111">Requirements</span></span>  
 <span data-ttu-id="506a5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="506a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="506a5-113">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="506a5-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="506a5-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="506a5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="506a5-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="506a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="506a5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="506a5-116">See Also</span></span>  
 [<span data-ttu-id="506a5-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="506a5-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="506a5-118">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="506a5-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="506a5-119">Кокласс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="506a5-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
