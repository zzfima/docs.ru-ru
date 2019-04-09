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
ms.openlocfilehash: 75bef91eb70c8109653741452362cd2e85f625ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138142"
---
# <a name="igchost2-interface"></a><span data-ttu-id="35a07-102">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="35a07-102">IGCHost2 Interface</span></span>
<span data-ttu-id="35a07-103">Предоставляет методы для получения информации о сборщик мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="35a07-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35a07-104">Для разработки новых приложений мы рекомендуем использовать [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="35a07-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35a07-105">Методы</span><span class="sxs-lookup"><span data-stu-id="35a07-105">Methods</span></span>  
  
|<span data-ttu-id="35a07-106">Метод</span><span class="sxs-lookup"><span data-stu-id="35a07-106">Method</span></span>|<span data-ttu-id="35a07-107">Описание</span><span class="sxs-lookup"><span data-stu-id="35a07-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35a07-108">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="35a07-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="35a07-109">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="35a07-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="35a07-110">Позволяет поколения 0 и размера сегментов, размер которых превышает `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="35a07-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35a07-111">Требования</span><span class="sxs-lookup"><span data-stu-id="35a07-111">Requirements</span></span>  
 <span data-ttu-id="35a07-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a07-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a07-113">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="35a07-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="35a07-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35a07-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="35a07-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="35a07-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35a07-116">См. также</span><span class="sxs-lookup"><span data-stu-id="35a07-116">See also</span></span>

- [<span data-ttu-id="35a07-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="35a07-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="35a07-118">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="35a07-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="35a07-119">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="35a07-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
