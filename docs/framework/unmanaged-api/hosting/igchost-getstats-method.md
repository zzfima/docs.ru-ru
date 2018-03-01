---
title: "Метод IGCHost::GetStats"
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
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d105b0aed9c47d5e2d8ad664744e6424db63961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="ccc18-102">Метод IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="ccc18-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="ccc18-103">Получает статистику для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ccc18-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccc18-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccc18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccc18-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="ccc18-106">[in, out] Указатель на [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуру, которая содержит статистические данные для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ccc18-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccc18-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccc18-107">Remarks</span></span>  
 <span data-ttu-id="ccc18-108">Статистика может использоваться системой оптимального распределения для работы системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="ccc18-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="ccc18-109">Например система распределения может определить после получения статистики, нужно увеличить объем памяти или принудительно коллекцию.</span><span class="sxs-lookup"><span data-stu-id="ccc18-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc18-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ccc18-110">Requirements</span></span>  
 <span data-ttu-id="ccc18-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc18-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc18-112">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="ccc18-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ccc18-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccc18-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccc18-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc18-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc18-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc18-115">See Also</span></span>  
 [<span data-ttu-id="ccc18-116">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="ccc18-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
