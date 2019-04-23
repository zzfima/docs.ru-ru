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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177740"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="6060e-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="6060e-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="6060e-103">Содержит статистику по потокам, относящиеся к сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="6060e-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6060e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6060e-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="6060e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6060e-105">Members</span></span>  
  
|<span data-ttu-id="6060e-106">Член</span><span class="sxs-lookup"><span data-stu-id="6060e-106">Member</span></span>|<span data-ttu-id="6060e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6060e-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="6060e-108">Число байтов памяти, выделенный в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6060e-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="6060e-109">Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="6060e-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="6060e-110">Число байтов, продвигаются в поколение более высокого уровня на последний сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="6060e-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6060e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6060e-111">Remarks</span></span>  
 <span data-ttu-id="6060e-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="6060e-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6060e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6060e-113">Requirements</span></span>  
 <span data-ttu-id="6060e-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6060e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6060e-115">**Заголовок.** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="6060e-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="6060e-116">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6060e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6060e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6060e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6060e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6060e-118">See also</span></span>

- [<span data-ttu-id="6060e-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="6060e-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="6060e-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="6060e-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
