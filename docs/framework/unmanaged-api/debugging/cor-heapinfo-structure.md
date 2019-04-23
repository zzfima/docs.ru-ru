---
title: Структура COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090359"
---
# <a name="corheapinfo-structure"></a>Структура COR_HEAPINFO
Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` Если структурами для сборки мусора являются допустимыми и могут быть перечислены кучи; в противном случае `false`.|  
|`pointerSize`|Размер в байтах, указателей в целевой архитектуре.|  
|`numHeaps`|Количество логических мусора кучи в процессе.|  
|`concurrent`|`TRUE` Если параллельный сбор мусора (фон) включена; в противном случае `FALSE`.|  
|`gcType`|Является членом [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) перечисление, указывающее, выполняется ли сборщик мусора на рабочей станции или сервера.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `COR_HEAPINFO` структура возвращается путем вызова [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.  
  
 Прежде чем перечисление объектов в куче сбора мусора, всегда необходимо проверять `areGCStructuresValid` чтобы убедиться, что кучи находится в состоянии перечисляемый. Дополнительные сведения см. в разделе [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
