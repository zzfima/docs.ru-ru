---
title: Структура CorDebugBlockingObject
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740395"
---
# <a name="cordebugblockingobject-structure"></a>Структура CorDebugBlockingObject
Определяет объект, блокирующий поток и особых причин, что поток блокируется.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`pBlockingObject`|Объект, на котором блокирован поток. Этот объект действителен только в течение текущего синхронизированного состояния. Если два потока блокируются на один и тот же объект в этом же состоянии, можно ожидать [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) метод, чтобы возвращать то же значение. Однако интерфейсы могут или не может быть указателем эквивалент.|  
|`dwTimeout`|Количество миллисекунд до операции блокирования будет время ожидания, или значение INFINITE, означающее, что он будет время ожидания не истекает. Значение времени ожидания указывает общую длину времени блокирующие операции, не осталось времени.|  
|`blockingReason`|Причина, что поток блокируется на этот объект.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
