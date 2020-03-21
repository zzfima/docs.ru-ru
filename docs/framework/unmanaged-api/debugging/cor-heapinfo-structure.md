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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179312"
---
# <a name="cor_heapinfo-structure"></a>Структура COR_HEAPINFO
Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Члены  
  
|Участник|Описание|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`если структуры сбора мусора действительны и куча может быть перечислена; в `false`противном случае, .|  
|`pointerSize`|Размер, в байтах, указателей на целевую архитектуру.|  
|`numHeaps`|Количество логических кучи сбора мусора в процессе.|  
|`concurrent`|`TRUE`если включен параллельный (фоновый) сбор мусора; в `FALSE`противном случае, .|  
|`gcType`|Участник перечисления [CorDebugGCType,](cordebuggctype-enumeration.md) указывающий, работает ли сборщик мусора на рабочей станции или сервере.|  
  
## <a name="remarks"></a>Remarks  
 Экземпляр `COR_HEAPINFO` структуры возвращается, позвонив методi [ICorDebugProcess5:GetGCHeapInformation.](icordebugprocess5-getgcheapinformation-method.md)  
  
 Прежде чем перечислять объекты на куче сбора мусора, вы всегда должны проверить `areGCStructuresValid` поле, чтобы убедиться, что куча находится в перечисленном состоянии. Для получения дополнительной [информации](icordebugprocess5-getgcheapinformation-method.md) см.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры отладки](debugging-structures.md)
- [Отладки](index.md)
