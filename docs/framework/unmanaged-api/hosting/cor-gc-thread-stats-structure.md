---
title: "Структура COR_GC_THREAD_STATS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 266352984cf50dc906e77598e8dcc9216526ce17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="294f0-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="294f0-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="294f0-103">Содержит статистику потоков сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="294f0-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="294f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="294f0-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="294f0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="294f0-105">Members</span></span>  
  
|<span data-ttu-id="294f0-106">Член</span><span class="sxs-lookup"><span data-stu-id="294f0-106">Member</span></span>|<span data-ttu-id="294f0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="294f0-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="294f0-108">Число байтов памяти, выделенной в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="294f0-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="294f0-109">Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="294f0-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="294f0-110">Число байтов продвигаются в поколение более высокого уровня при самой последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="294f0-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="294f0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="294f0-111">Remarks</span></span>  
 <span data-ttu-id="294f0-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="294f0-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="294f0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="294f0-113">Requirements</span></span>  
 <span data-ttu-id="294f0-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="294f0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="294f0-115">**Заголовок:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="294f0-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="294f0-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="294f0-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="294f0-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="294f0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="294f0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="294f0-118">See Also</span></span>  
 [<span data-ttu-id="294f0-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="294f0-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="294f0-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="294f0-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
