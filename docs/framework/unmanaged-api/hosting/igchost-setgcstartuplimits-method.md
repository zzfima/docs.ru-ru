---
title: "Метод IGCHost::SetGCStartupLimits"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d99212b1ece4d3c0ce9440ac973b8254ebca6dde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="4aa3a-102">Метод IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="4aa3a-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="4aa3a-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4aa3a-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно задать размер сегмента и максимальное поколения 0 размер значения больше, чем `DWORD` с помощью [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa3a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4aa3a-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aa3a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4aa3a-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="4aa3a-107">[in] Размер сегментов, используемых сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="4aa3a-108">[in] Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4aa3a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4aa3a-109">Remarks</span></span>  
 <span data-ttu-id="4aa3a-110">`SetGCStartupLimits` Метод может вызываться только один раз.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="4aa3a-111">Эти значения невозможно изменить позже.</span><span class="sxs-lookup"><span data-stu-id="4aa3a-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aa3a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4aa3a-112">Requirements</span></span>  
 <span data-ttu-id="4aa3a-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aa3a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aa3a-114">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4aa3a-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4aa3a-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4aa3a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4aa3a-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aa3a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa3a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4aa3a-117">See Also</span></span>  
 [<span data-ttu-id="4aa3a-118">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="4aa3a-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
