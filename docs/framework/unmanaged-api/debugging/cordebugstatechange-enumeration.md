---
title: Перечисление CorDebugStateChange
ms.date: 03/30/2017
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f0f692b692628d50755ce813c66823f940dccb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513793"
---
# <a name="cordebugstatechange-enumeration"></a>Перечисление CorDebugStateChange
Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`PROCESS_RUNNING`|Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|Память процесса может отличаться произвольным образом от предыдущего варианта.|  
  
## <a name="remarks"></a>Примечания  
 Является членом `CorDebugStateChange` перечисление предоставляется в качестве аргумента при вызове отладчиком [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) метод  
  
> [!NOTE]
>  Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
