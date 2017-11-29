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
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="01229-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="01229-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="01229-103">Содержит статистику потоков сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="01229-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01229-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01229-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="01229-105">Члены</span><span class="sxs-lookup"><span data-stu-id="01229-105">Members</span></span>  
  
|<span data-ttu-id="01229-106">Член</span><span class="sxs-lookup"><span data-stu-id="01229-106">Member</span></span>|<span data-ttu-id="01229-107">Описание</span><span class="sxs-lookup"><span data-stu-id="01229-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="01229-108">Число байтов памяти, выделенной в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="01229-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="01229-109">Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="01229-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="01229-110">Число байтов продвигаются в поколение более высокого уровня при самой последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="01229-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01229-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="01229-111">Remarks</span></span>  
 <span data-ttu-id="01229-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="01229-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01229-113">Требования</span><span class="sxs-lookup"><span data-stu-id="01229-113">Requirements</span></span>  
 <span data-ttu-id="01229-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01229-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01229-115">**Заголовок:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="01229-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="01229-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01229-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01229-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01229-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01229-118">См. также</span><span class="sxs-lookup"><span data-stu-id="01229-118">See Also</span></span>  
 [<span data-ttu-id="01229-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="01229-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="01229-120">IHostTask-интерфейс</span><span class="sxs-lookup"><span data-stu-id="01229-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
