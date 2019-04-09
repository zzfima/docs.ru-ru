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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177740"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="2f3eb-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="2f3eb-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="2f3eb-103">Содержит статистику по потокам, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="2f3eb-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f3eb-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="2f3eb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2f3eb-105">Members</span></span>  
  
|<span data-ttu-id="2f3eb-106">Член</span><span class="sxs-lookup"><span data-stu-id="2f3eb-106">Member</span></span>|<span data-ttu-id="2f3eb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2f3eb-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="2f3eb-108">Число байтов памяти, выделенный в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2f3eb-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="2f3eb-109">Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="2f3eb-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="2f3eb-110">Число байтов, продвигаются в поколение более высокого уровня на последний сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="2f3eb-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3eb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f3eb-111">Remarks</span></span>  
 <span data-ttu-id="2f3eb-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="2f3eb-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3eb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2f3eb-113">Requirements</span></span>  
 <span data-ttu-id="2f3eb-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f3eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3eb-115">**Заголовок.** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="2f3eb-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="2f3eb-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f3eb-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2f3eb-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2f3eb-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f3eb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2f3eb-118">See also</span></span>

- [<span data-ttu-id="2f3eb-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="2f3eb-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="2f3eb-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="2f3eb-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
