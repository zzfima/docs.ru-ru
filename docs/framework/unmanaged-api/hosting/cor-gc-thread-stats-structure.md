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
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136989"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="9d732-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="9d732-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="9d732-103">Содержит статистику по каждому потоку, относящуюся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9d732-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d732-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d732-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="9d732-105">Члены</span><span class="sxs-lookup"><span data-stu-id="9d732-105">Members</span></span>  
  
|<span data-ttu-id="9d732-106">Член</span><span class="sxs-lookup"><span data-stu-id="9d732-106">Member</span></span>|<span data-ttu-id="9d732-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9d732-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="9d732-108">Число байтов памяти, выделенных в потоке, связанном с текущим экземпляром `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="9d732-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="9d732-109">Это число сбрасывается в ноль каждый раз, когда происходит сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="9d732-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="9d732-110">Число байтов, преобразованных в более высокое поколение при последней сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="9d732-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d732-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="9d732-111">Remarks</span></span>  
 <span data-ttu-id="9d732-112">[ICLRTask:: жетмемстатс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="9d732-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d732-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9d732-113">Requirements</span></span>  
 <span data-ttu-id="9d732-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d732-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d732-115">**Заголовок:** Гчост. idl</span><span class="sxs-lookup"><span data-stu-id="9d732-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="9d732-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d732-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d732-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d732-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d732-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9d732-118">See also</span></span>

- [<span data-ttu-id="9d732-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="9d732-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="9d732-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="9d732-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
