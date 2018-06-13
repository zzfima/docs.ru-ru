---
title: Перечисление COR_GC_STAT_TYPES
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eac378a48900d5820ad35587a6d269648ef99a77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428903"
---
# <a name="corgcstattypes-enumeration"></a>Перечисление COR_GC_STAT_TYPES
Указывает статистику, записываемую для сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Примечания  
 Это перечисление указывает, какая именно статистика в [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) структуры должны задаваться [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) метод.  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Записи количество сборок мусора, выполненных для каждого поколения.|  
|`COR_GC_MEMORYUSAGE`|Записи об использовании и сборке мусора коллекции размер статистику памяти.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl, GCHost.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структура COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
