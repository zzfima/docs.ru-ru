---
title: Структура COR_GC_THREAD_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178269"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="73039-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="73039-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="73039-103">Содержит статистику по потоку, относящуюся к сбору мусора.</span><span class="sxs-lookup"><span data-stu-id="73039-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73039-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73039-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="73039-105">Члены</span><span class="sxs-lookup"><span data-stu-id="73039-105">Members</span></span>  
  
|<span data-ttu-id="73039-106">Участник</span><span class="sxs-lookup"><span data-stu-id="73039-106">Member</span></span>|<span data-ttu-id="73039-107">Описание</span><span class="sxs-lookup"><span data-stu-id="73039-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="73039-108">Количество байтов памяти, выделенных на потоке, связанном с текущим `COR_GC_THREAD_STATS` экземпляром.</span><span class="sxs-lookup"><span data-stu-id="73039-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="73039-109">Это число очищается до нуля каждый раз, когда происходит сбор мусора с нулевым поколением.</span><span class="sxs-lookup"><span data-stu-id="73039-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="73039-110">Количество байтов, повышенных до более высокого поколения на последнем сборе мусора.</span><span class="sxs-lookup"><span data-stu-id="73039-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73039-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="73039-111">Remarks</span></span>  
 <span data-ttu-id="73039-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходный `COR_GC_THREAD_STATS`параметр типа.</span><span class="sxs-lookup"><span data-stu-id="73039-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73039-113">Требования</span><span class="sxs-lookup"><span data-stu-id="73039-113">Requirements</span></span>  
 <span data-ttu-id="73039-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73039-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73039-115">**Заголовок:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="73039-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="73039-116">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73039-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73039-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73039-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73039-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73039-118">See also</span></span>

- [<span data-ttu-id="73039-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="73039-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="73039-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="73039-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
