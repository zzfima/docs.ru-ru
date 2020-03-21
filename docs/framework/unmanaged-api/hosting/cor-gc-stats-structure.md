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
# <a name="cor_gc_stats-structure"></a>Структура COR_GC_STATS
Предоставляет статистику о механизме сбора мусора общего языка времени выполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`Flags`|Указывает, какие значения поля должны быть рассчитаны и возвращены.|  
|`ExplicitGCCount`|Указывает количество сборов мусора, которые были вынуждены по внешнему запросу.|  
|`GenCollectionsTaken`|Указывает количество сборов мусора, выполняемых для каждого поколения.|  
|`CommittedKBytes`|Общее количество килобайт, совершенных во всех кучи.|  
|`ReservedKBytes`|Общее количество килобайт зарезервировано во всех кучи.|  
|`Gen0HeapSizeKBytes`|Размер, в килобайтах, поколения нулевой кучи.|  
|`Gen1HeapSizeKBytes`|Размер, в килобайтах, поколения-один кучи.|  
|`Gen2HeapSizeKBytes`|Размер, в килобайтах, поколения два кучи.|  
|`LargeObjectHeapSizeKBytes`|Размер, в килобайтах, большой кучи объекта.|  
|`KBytesPromotedFromGen0`|Размер, в килобайтах, объектов, продвигаемых от нуля поколения до поколения один.|  
|`KBytesPromotedFromGen1`|Размер, в килобайтах, объектов, продвигаемых от поколения одного до поколения два.|  
  
## <a name="remarks"></a>Remarks  
 Метод [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) требует, чтобы `Flags` поле `COR_GC_STATS` структуры было установлено на одно или несколько значений [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисления, чтобы указать, какие статистические данные должны быть установлены.  
  
 В следующей таблице приведены статистические данные, представленные этой `COR_GC_COUNTS` `COR_GC_MEMORYUSAGE`структурой, к двум [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) значениям перечисления и .  
  
|Уточняется, COR_GC_COUNTS|Уточняется, COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Пример использования:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Сборка мусора](../../../standard/garbage-collection/index.md)
