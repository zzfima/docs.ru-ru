---
title: Метод IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe94aa67c9cf9ac587b7fca9f5cbeca4870506b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="4b16e-102">Метод IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="4b16e-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="4b16e-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="4b16e-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b16e-104">Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно задать размер сегмента и максимальное поколения 0 размер значения больше, чем `DWORD` с помощью [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4b16e-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b16e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b16e-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b16e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4b16e-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="4b16e-107">[in] Размер сегментов, используемых сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="4b16e-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="4b16e-108">[in] Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="4b16e-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b16e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b16e-109">Remarks</span></span>  
 <span data-ttu-id="4b16e-110">`SetGCStartupLimits` Метод может вызываться только один раз.</span><span class="sxs-lookup"><span data-stu-id="4b16e-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="4b16e-111">Эти значения невозможно изменить позже.</span><span class="sxs-lookup"><span data-stu-id="4b16e-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b16e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4b16e-112">Requirements</span></span>  
 <span data-ttu-id="4b16e-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b16e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b16e-114">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4b16e-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4b16e-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b16e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b16e-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b16e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b16e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4b16e-117">See Also</span></span>  
 [<span data-ttu-id="4b16e-118">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="4b16e-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
