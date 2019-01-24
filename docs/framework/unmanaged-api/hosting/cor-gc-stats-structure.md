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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fc212321b28545f62f0a1c2965281d02ac73e40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638110"
---
# <a name="corgcstats-structure"></a><span data-ttu-id="9cd0c-102">Структура COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="9cd0c-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="9cd0c-103">Предоставляет статистику механизм сбора мусора общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9cd0c-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cd0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cd0c-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="9cd0c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9cd0c-105">Members</span></span>  
  
|<span data-ttu-id="9cd0c-106">Член</span><span class="sxs-lookup"><span data-stu-id="9cd0c-106">Member</span></span>|<span data-ttu-id="9cd0c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9cd0c-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="9cd0c-108">Указывает, вычисления и возвращаемых значений полей, которые.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="9cd0c-109">Указывает номер сборки мусора, которые были принудительно с помощью внешнего запроса.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="9cd0c-110">Указывает число сборов мусора, выполненных для каждого поколения.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="9cd0c-111">Общее число килобайтов зафиксированных во всех кучах.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="9cd0c-112">Общее число килобайтов зарезервированных во всех кучах.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="9cd0c-113">Размер в килобайтах, нулевого поколения кучи.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="9cd0c-114">Размер в килобайтах, кучи поколения.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="9cd0c-115">Размер в килобайтах, кучи второго поколения.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="9cd0c-116">Размер в килобайтах, куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="9cd0c-117">Размер в килобайтах, объектов, перенесенных из нулевого поколения, одно.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="9cd0c-118">Размер в килобайтах, перенесенных из первого поколения двух объектов.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cd0c-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cd0c-119">Remarks</span></span>  
 <span data-ttu-id="9cd0c-120">[ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод требует `Flags` поле `COR_GC_STATS` структура будет присвоено одно или несколько значений из [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисления, чтобы указать, какие Статистика устанавливаемое значение.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="9cd0c-121">В таблице ниже приведены статистические данные, предоставляемые этой структуры к двум [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) значений перечисления, `COR_GC_COUNTS` и `COR_GC_MEMORYUSAGE`.</span><span class="sxs-lookup"><span data-stu-id="9cd0c-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="9cd0c-122">Определяемое COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="9cd0c-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="9cd0c-123">Определяемое COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="9cd0c-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="9cd0c-124">Ниже приведен пример использования:</span><span class="sxs-lookup"><span data-stu-id="9cd0c-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9cd0c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="9cd0c-125">Requirements</span></span>  
 <span data-ttu-id="9cd0c-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cd0c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cd0c-127">**Заголовок.** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="9cd0c-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="9cd0c-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9cd0c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cd0c-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cd0c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd0c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="9cd0c-130">See also</span></span>
- [<span data-ttu-id="9cd0c-131">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="9cd0c-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="9cd0c-132">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="9cd0c-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="9cd0c-133">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="9cd0c-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
