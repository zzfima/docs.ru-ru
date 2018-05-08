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
ms.openlocfilehash: 8fb1ae367c30bb038bfe25961e91f02f172f486c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|`pointerSize`|Размер в байтах указателей в целевой архитектуре.|  
|`numHeaps`|Количество логических мусора кучи в процессе.|  
|`concurrent`|`TRUE` Если параллельной сборки мусора (фонового) включена; в противном случае `FALSE`.|  
|`gcType`|Член [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) перечисление, указывающее, выполняется ли сборщик мусора на рабочей станции или сервере.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `COR_HEAPINFO` структуры, возвращенный при вызове [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.  
  
 Перед перечисление объектов в куче сбора мусора, необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедитесь, что в состоянии перечисляемую кучи. Дополнительные сведения см. в разделе [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
