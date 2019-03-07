---
title: Метод IGCHost::GetThreadStats
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92911469383e9e8a1484eff4dedfaf61117e5982
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496265"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="37bae-102">Метод IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="37bae-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="37bae-103">Получает статистику по потокам для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="37bae-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37bae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37bae-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37bae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37bae-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="37bae-106">[in] Указатель на Многослойный файл cookie, указывающее поток, для которого требуется извлечь статистику.</span><span class="sxs-lookup"><span data-stu-id="37bae-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="37bae-107">[in, out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) структуру, содержащую статистику сбора мусора для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="37bae-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37bae-108">Требования</span><span class="sxs-lookup"><span data-stu-id="37bae-108">Requirements</span></span>  
 <span data-ttu-id="37bae-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37bae-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37bae-110">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="37bae-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="37bae-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37bae-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37bae-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37bae-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37bae-113">См. также</span><span class="sxs-lookup"><span data-stu-id="37bae-113">See also</span></span>
- [<span data-ttu-id="37bae-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="37bae-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
