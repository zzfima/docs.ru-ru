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
ms.openlocfilehash: 24a386fe82bbd004954924a573c090af7f58824a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="69edb-102">Структура COR_GC_THREAD_STATS</span><span class="sxs-lookup"><span data-stu-id="69edb-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="69edb-103">Содержит статистику потоков сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="69edb-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69edb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69edb-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="69edb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="69edb-105">Members</span></span>  
  
|<span data-ttu-id="69edb-106">Член</span><span class="sxs-lookup"><span data-stu-id="69edb-106">Member</span></span>|<span data-ttu-id="69edb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="69edb-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="69edb-108">Число байтов памяти, выделенной в потоке, который связан с текущим `COR_GC_THREAD_STATS` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="69edb-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="69edb-109">Это число обнуляется каждый раз, когда выполняется сборка мусора нулевого поколения.</span><span class="sxs-lookup"><span data-stu-id="69edb-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="69edb-110">Число байтов продвигаются в поколение более высокого уровня при самой последней сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="69edb-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69edb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="69edb-111">Remarks</span></span>  
 <span data-ttu-id="69edb-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) принимает выходной параметр типа `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="69edb-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69edb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="69edb-113">Requirements</span></span>  
 <span data-ttu-id="69edb-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69edb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69edb-115">**Заголовок:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="69edb-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="69edb-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69edb-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69edb-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69edb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69edb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="69edb-118">See Also</span></span>  
 [<span data-ttu-id="69edb-119">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="69edb-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="69edb-120">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="69edb-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
