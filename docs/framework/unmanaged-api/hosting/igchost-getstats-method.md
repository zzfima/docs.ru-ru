---
title: Метод IGCHost::GetStats
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3e0d6f68ffa5280d4616d4fa4ac60b4cb86f6a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437769"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="0d422-102">Метод IGCHost::GetStats</span><span class="sxs-lookup"><span data-stu-id="0d422-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="0d422-103">Получает статистику для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d422-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d422-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d422-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d422-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d422-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="0d422-106">[in, out] Указатель на [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуру, которая содержит статистические данные для текущего состояния системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d422-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d422-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d422-107">Remarks</span></span>  
 <span data-ttu-id="0d422-108">Статистика может использоваться системой оптимального распределения для работы системы сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="0d422-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="0d422-109">Например система распределения может определить после получения статистики, нужно увеличить объем памяти или принудительно коллекцию.</span><span class="sxs-lookup"><span data-stu-id="0d422-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d422-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0d422-110">Requirements</span></span>  
 <span data-ttu-id="0d422-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d422-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d422-112">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="0d422-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0d422-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d422-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d422-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d422-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d422-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0d422-115">See Also</span></span>  
 [<span data-ttu-id="0d422-116">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="0d422-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
