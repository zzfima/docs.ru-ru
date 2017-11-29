---
title: "Метод IGCHost::GetStats"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8db4f854b73d04e7260457c978a7a644677559
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="74a83-102">Метод IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="74a83-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="74a83-103">Получает статистику для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="74a83-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74a83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74a83-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74a83-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="74a83-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="74a83-106">[in, out] Указатель на [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуру, которая содержит статистические данные для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="74a83-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74a83-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="74a83-107">Remarks</span></span>  
 <span data-ttu-id="74a83-108">Статистика может использоваться системой оптимального распределения для работы системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="74a83-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="74a83-109">Например система распределения может определить после получения статистики, нужно увеличить объем памяти или принудительно коллекцию.</span><span class="sxs-lookup"><span data-stu-id="74a83-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74a83-110">Требования</span><span class="sxs-lookup"><span data-stu-id="74a83-110">Requirements</span></span>  
 <span data-ttu-id="74a83-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74a83-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74a83-112">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="74a83-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="74a83-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74a83-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74a83-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74a83-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a83-115">См. также</span><span class="sxs-lookup"><span data-stu-id="74a83-115">See Also</span></span>  
 [<span data-ttu-id="74a83-116">Igchost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="74a83-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
