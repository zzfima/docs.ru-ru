---
title: Структура COR_GC_STATS
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176530"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="60dca-102">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="60dca-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="60dca-103">Предоставляет статистику о механизме сбора мусора общего языка времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="60dca-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60dca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60dca-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="60dca-105">Члены</span><span class="sxs-lookup"><span data-stu-id="60dca-105">Members</span></span>  
  
|<span data-ttu-id="60dca-106">Участник</span><span class="sxs-lookup"><span data-stu-id="60dca-106">Member</span></span>|<span data-ttu-id="60dca-107">Описание</span><span class="sxs-lookup"><span data-stu-id="60dca-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="60dca-108">Указывает, какие значения поля должны быть рассчитаны и возвращены.</span><span class="sxs-lookup"><span data-stu-id="60dca-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="60dca-109">Указывает количество сборов мусора, которые были вынуждены по внешнему запросу.</span><span class="sxs-lookup"><span data-stu-id="60dca-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="60dca-110">Указывает количество сборов мусора, выполняемых для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="60dca-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="60dca-111">Общее количество килобайт, совершенных во всех кучи.</span><span class="sxs-lookup"><span data-stu-id="60dca-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="60dca-112">Общее количество килобайт зарезервировано во всех кучи.</span><span class="sxs-lookup"><span data-stu-id="60dca-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="60dca-113">Размер, в килобайтах, поколения нулевой кучи.</span><span class="sxs-lookup"><span data-stu-id="60dca-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="60dca-114">Размер, в килобайтах, поколения-один кучи.</span><span class="sxs-lookup"><span data-stu-id="60dca-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="60dca-115">Размер, в килобайтах, поколения два кучи.</span><span class="sxs-lookup"><span data-stu-id="60dca-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="60dca-116">Размер, в килобайтах, большой кучи объекта.</span><span class="sxs-lookup"><span data-stu-id="60dca-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="60dca-117">Размер, в килобайтах, объектов, продвигаемых от нуля поколения до поколения один.</span><span class="sxs-lookup"><span data-stu-id="60dca-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="60dca-118">Размер, в килобайтах, объектов, продвигаемых от поколения одного до поколения два.</span><span class="sxs-lookup"><span data-stu-id="60dca-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60dca-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="60dca-119">Remarks</span></span>  
 <span data-ttu-id="60dca-120">Метод [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) требует, чтобы `Flags` поле `COR_GC_STATS` структуры было установлено на одно или несколько значений [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисления, чтобы указать, какие статистические данные должны быть установлены.</span><span class="sxs-lookup"><span data-stu-id="60dca-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="60dca-121">В следующей таблице приведены статистические данные, представленные этой `COR_GC_COUNTS` `COR_GC_MEMORYUSAGE`структурой, к двум [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) значениям перечисления и .</span><span class="sxs-lookup"><span data-stu-id="60dca-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="60dca-122">Уточняется, COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="60dca-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="60dca-123">Уточняется, COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="60dca-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="60dca-124">Пример использования:</span><span class="sxs-lookup"><span data-stu-id="60dca-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="60dca-125">Требования</span><span class="sxs-lookup"><span data-stu-id="60dca-125">Requirements</span></span>  
 <span data-ttu-id="60dca-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60dca-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60dca-127">**Заголовок:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="60dca-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="60dca-128">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60dca-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60dca-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60dca-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60dca-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="60dca-130">See also</span></span>

- [<span data-ttu-id="60dca-131">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="60dca-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="60dca-132">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="60dca-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="60dca-133">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="60dca-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
