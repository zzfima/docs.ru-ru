---
title: "Метод IGCHost::GetThreadStats"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fe84dd4d231bacba6792836844058b7256124db5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="08640-102">Метод IGCHost::GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="08640-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="08640-103">Получает статистику отдельного потока для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="08640-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08640-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08640-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08640-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08640-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="08640-106">[in] Указатель Многослойный файл cookie, указывающее поток, для которого требуется извлечь статистику.</span><span class="sxs-lookup"><span data-stu-id="08640-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="08640-107">[in, out] Указатель на [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) структуру, содержащую статистику сборки мусора для заданного потока.</span><span class="sxs-lookup"><span data-stu-id="08640-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08640-108">Требования</span><span class="sxs-lookup"><span data-stu-id="08640-108">Requirements</span></span>  
 <span data-ttu-id="08640-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08640-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08640-110">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="08640-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="08640-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08640-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08640-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08640-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08640-113">См. также</span><span class="sxs-lookup"><span data-stu-id="08640-113">See Also</span></span>  
 [<span data-ttu-id="08640-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="08640-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
