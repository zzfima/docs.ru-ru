---
title: Интерфейс ICorDebugType
ms.date: 03/30/2017
api_name:
- ICorDebugType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType
helpviewer_keywords:
- ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type:
- apiref
ms.openlocfilehash: 4f3f553ed5dc93433610365e0dae5bee54863de5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129627"
---
# <a name="icordebugtype-interface"></a>Интерфейс ICorDebugType
Представляет тип — базовый или сложный (то есть определяемый пользователем). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные параметры <xref:System.Type> класса, на который ссылается этот `ICorDebugType`.|  
|[Метод GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Возвращает указатель интерфейса на `ICorDebugType`, ссылающийся на базовый класс класса, на который ссылается этот `ICorDebugType`, если он существует.|  
|[Метод GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого `ICorDebugType`.|  
|[Метод GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Возвращает указатель интерфейса на `ICorDebugType`, который ссылается на первый универсальный параметр <xref:System.Type> для конструктора класса, на который ссылается этот `ICorDebugType`.|  
|[Метод GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Возвращает число измерений в типе массива.|  
|[Метод GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Возвращает значение Корелементтипе, описывающее собственный тип среды CLR <xref:System.Type> на которую ссылается этот `ICorDebugType`.|  
  
## <a name="remarks"></a>Заметки  
 Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром. Интерфейс `ICorDebugType` представляет экземпляр универсального типа. Например, хэш-таблица\<K, V > будет представлена `ICorDebugClass`, тогда как Hashtable\<Int32, строка > будет представлена `ICorDebugType`.  
  
 Типы, не являющиеся универсальными, представляются как `ICorDebugClass`, так и `ICorDebugType`. Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
