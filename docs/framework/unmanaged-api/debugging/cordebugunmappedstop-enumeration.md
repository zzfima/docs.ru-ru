---
title: Перечисление CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: cc02f63808b1929b93777c8bbc67c47000b0b424
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132751"
---
# <a name="cordebugunmappedstop-enumeration"></a>Перечисление CorDebugUnmappedStop
Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`STOP_NONE`|Не останавливайте в любом типе несопоставленного кода.|  
|`STOP_PROLOG`|Останавливает в коде пролога.|  
|`STOP_EPILOG`|Прерывать в коде эпилога.|  
|`STOP_NO_MAPPING_INFO`|Прерывать в коде, не имеющем сведений о сопоставлении.|  
|`STOP_OTHER_UNMAPPED`|Прерывать в несопоставленном коде, который не помещается ни в прологе, ни в том, ни в какую информацию, ни в неуправляемой категории.|  
|`STOP_UNMANAGED`|Останавливает в неуправляемом коде. Это значение допустимо только при отладке взаимодействия.|  
|`STOP_ALL`|Останавливаются во всех типах несопоставленного кода.|  
  
## <a name="remarks"></a>Заметки  
 Используйте метод [ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) , чтобы задать флаги, указывающие Несопоставленный код, в котором будет останавливаться средство Организации.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
