---
title: Перечисление CorGCReferenceType
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a673c98b11fbca5f66e9e1ae61f224448c20797
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966209"
---
# <a name="corgcreferencetype-enumeration"></a>Перечисление CorGCReferenceType
Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Участники  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`CorHandleStrong`|Дескриптор строгой ссылки из таблицы дескрипторов объектов.|  
|`CorHandleStrongPinning`|Дескриптор закрепленная строгая ссылка из таблицы дескрипторов объектов.|  
|`CorHandleWeakShort`|Дескриптор слабая ссылка из таблицы дескрипторов объектов.|  
|`CorHandleWeakRefCount`|Дескриптор объекта слабые подсчетом ссылок из таблицы дескрипторов объектов.|  
|`CorHandleStrongRefCount`|Дескриптор в объект с подсчетом ссылок из таблицы дескрипторов объектов.|  
|`CorHandleStrongDependent`|Дескриптор зависимого объекта из таблицы дескрипторов объектов.|  
|`CorHandleStrongAsyncPinned`|Асинхронный закрепленный объект из таблицы дескрипторов объектов.|  
|`CorHandleStrongSizedByref`|Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.|  
|`CorReferenceStack`|Ссылка из управляемого стека.|  
|`CorReferenceFinalizer`|Ссылка из очереди метода завершения.|  
|CorHandleStrongOnly|Возвращать только строгих ссылок из таблицы дескрипторов. Это значение используется по [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
|`CorHandleWeakOnly`|Возвращать только слабые ссылки из таблицы дескрипторов. Это значение используется по [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
|`CorHandleAll`|Возврат всех ссылок из таблицы дескрипторов. Это значение используется по [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
  
## <a name="remarks"></a>Примечания  
 `CorGCReferenceType` Перечисление используется следующим образом:  
  
- Для параметра `type` поле [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) структуры, он указывает на источник ссылки или дескриптора.  
  
- Как `types` аргумент [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) метод, он указывает типы обработчиков, чтобы включить в перечисление.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
