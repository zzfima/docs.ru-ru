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
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793866"
---
# <a name="corgcreferencetype-enumeration"></a>Перечисление CorGCReferenceType
Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
|Имя элемента|Описание|  
|-----------------|-----------------|  
|`CorHandleStrong`|Дескриптор строгой ссылки из таблицы дескрипторов объектов.|  
|`CorHandleStrongPinning`|Указатель на закрепленную строгую ссылку из таблицы обработчика объектов.|  
|`CorHandleWeakShort`|Указатель на слабую ссылку из таблицы обработчика объектов.|  
|`CorHandleWeakRefCount`|Указатель на слабый объект, подсчитанный по ссылке, из таблицы обработчика объектов.|  
|`CorHandleStrongRefCount`|Указатель на объект, подсчитанный по ссылке, из таблицы обработчика объектов.|  
|`CorHandleStrongDependent`|Маркер зависимого объекта из таблицы обработчика объектов.|  
|`CorHandleStrongAsyncPinned`|Асинхронный закрепленный объект из таблицы дескрипторов объектов.|  
|`CorHandleStrongSizedByref`|Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.|  
|`CorReferenceStack`|Ссылка из управляемого стека.|  
|`CorReferenceFinalizer`|Ссылка из очереди метода завершения.|  
|корхандлестронгонли|Возвращать только строгие ссылки из таблицы Handle. Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleWeakOnly`|Возвращать только слабые ссылки из таблицы Handle. Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleAll`|Возвращает все ссылки из таблицы Handle. Это значение используется только методом [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
  
## <a name="remarks"></a>Заметки  
 Перечисление `CorGCReferenceType` используется следующим образом:  
  
- В качестве значения поля `type` структуры [COR_GC_REFERENCE](cor-gc-reference-structure.md) указывает источник ссылки или маркера.  
  
- В качестве аргумента `types` метода [метод ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) указывает типы дескрипторов, включаемых в перечисление.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
