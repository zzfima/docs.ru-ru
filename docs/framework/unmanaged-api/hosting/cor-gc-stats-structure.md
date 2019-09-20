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
ms.openlocfilehash: 1085bec812d797d3fbe4ea63ef447d4c466149f2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965061"
---
# <a name="cor_gc_stats-structure"></a>Структура COR_GC_STATS
Содержит статистические данные о механизме сборки мусора среды CLR.  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`Flags`|Указывает, какие значения полей должны вычисляться и возвращаться.|  
|`ExplicitGCCount`|Указывает количество сборок мусора, принудительно выполненных внешним запросом.|  
|`GenCollectionsTaken`|Указывает количество сборок мусора, выполненных для каждого поколения.|  
|`CommittedKBytes`|Общее число килобайтов, зафиксированных во всех кучах.|  
|`ReservedKBytes`|Общее количество килобайтов, зарезервированных во всех кучах.|  
|`Gen0HeapSizeKBytes`|Размер кучи нулевого поколения (в килобайтах).|  
|`Gen1HeapSizeKBytes`|Размер кучи поколения (в килобайтах).|  
|`Gen2HeapSizeKBytes`|Размер кучи второго поколения (в килобайтах).|  
|`LargeObjectHeapSizeKBytes`|Размер кучи больших объектов (в килобайтах).|  
|`KBytesPromotedFromGen0`|Размер (в килобайтах) объектов, перешедших из поколения 0 в поколение.|  
|`KBytesPromotedFromGen1`|Размер (в килобайтах) объектов, перешедших из поколения 1 в поколение 2.|  
  
## <a name="remarks"></a>Примечания  
 Метод [иклргкманажер:: stats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) требует, `Flags` чтобы поле `COR_GC_STATS` структуры было задано для одного или нескольких значений перечисления [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) , чтобы указать, какую статистику следует задать.  
  
 Следующая таблица сопоставляет статистику, предоставленную этой структурой, с двумя значениями перечисления [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md): `COR_GC_COUNTS` и `COR_GC_MEMORYUSAGE`.  
  
|Задается параметром COR_GC_COUNTS|Задается параметром COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Пример использования таков:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Гчост. idl  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Сборка мусора](../../../standard/garbage-collection/index.md)
