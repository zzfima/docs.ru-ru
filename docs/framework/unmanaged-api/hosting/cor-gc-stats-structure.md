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
ms.openlocfilehash: 630c365c8710388ae3e913bedece0fb710da7cd9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768136"
---
# <a name="corgcstats-structure"></a>Структура COR_GC_STATS
Предоставляет статистику механизм сбора мусора общеязыковой среды выполнения (CLR).  
  
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
|`Flags`|Указывает, вычисления и возвращаемых значений полей, которые.|  
|`ExplicitGCCount`|Указывает номер сборки мусора, которые были принудительно с помощью внешнего запроса.|  
|`GenCollectionsTaken`|Указывает число сборов мусора, выполненных для каждого поколения.|  
|`CommittedKBytes`|Общее число килобайтов зафиксированных во всех кучах.|  
|`ReservedKBytes`|Общее число килобайтов зарезервированных во всех кучах.|  
|`Gen0HeapSizeKBytes`|Размер в килобайтах, нулевого поколения кучи.|  
|`Gen1HeapSizeKBytes`|Размер в килобайтах, кучи поколения.|  
|`Gen2HeapSizeKBytes`|Размер в килобайтах, кучи второго поколения.|  
|`LargeObjectHeapSizeKBytes`|Размер в килобайтах, куча больших объектов.|  
|`KBytesPromotedFromGen0`|Размер в килобайтах, объектов, перенесенных из нулевого поколения, одно.|  
|`KBytesPromotedFromGen1`|Размер в килобайтах, перенесенных из первого поколения двух объектов.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод требует `Flags` поле `COR_GC_STATS` структура будет присвоено одно или несколько значений из [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) перечисления, чтобы указать, какие Статистика устанавливаемое значение.  
  
 В таблице ниже приведены статистические данные, предоставляемые этой структуры к двум [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) значений перечисления, `COR_GC_COUNTS` и `COR_GC_MEMORYUSAGE`.  
  
|Определяемое COR_GC_COUNTS|Определяемое COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Ниже приведен пример использования:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** GCHost.idl  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Автоматическое управление памятью](../../../../docs/standard/automatic-memory-management.md)
- [Сборка мусора](../../../../docs/standard/garbage-collection/index.md)
