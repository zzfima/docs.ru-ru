---
title: "Метод IGCHost2::SetGCStartupLimitsEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ae924447e38dfec8d365fe6cdc85e5dccb028714
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="8c715-102">Метод IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="8c715-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="8c715-103">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="8c715-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c715-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c715-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c715-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c715-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="8c715-106">[in] Размер сегментов, используемых сборщик мусора.</span><span class="sxs-lookup"><span data-stu-id="8c715-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8c715-107">[in] Максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="8c715-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c715-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c715-108">Remarks</span></span>  
 <span data-ttu-id="8c715-109">Значения, `SetGCStartupLimitsEx` наборы можно указать только в том случае, перед запуском узла.</span><span class="sxs-lookup"><span data-stu-id="8c715-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="8c715-110">Эти значения невозможно изменить позже.</span><span class="sxs-lookup"><span data-stu-id="8c715-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c715-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8c715-111">Requirements</span></span>  
 <span data-ttu-id="8c715-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c715-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c715-113">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="8c715-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8c715-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c715-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c715-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c715-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c715-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8c715-116">See Also</span></span>  
 [<span data-ttu-id="8c715-117">Igchost2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8c715-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
