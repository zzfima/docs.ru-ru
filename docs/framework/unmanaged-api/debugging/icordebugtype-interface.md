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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e3d1173ac6fb14a380cdbc99882fd9baee6552a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966038"
---
# <a name="icordebugtype-interface"></a>Интерфейс ICorDebugType
Представляет тип, базовый или сложный (который определяемый пользователем). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Получает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальный <xref:System.Type> параметры типа класса, который ссылается этот `ICorDebugType`.|  
|[Метод GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Получает указатель интерфейса на `ICorDebugType` , ссылающийся на класс, который ссылается этот базовый класс `ICorDebugType`, если таковой имеется.|  
|[Метод GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Получает указатель интерфейса на ICorDebugClass, который ссылается на типизированный конструктор `ICorDebugType`.|  
|[Метод GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Получает указатель интерфейса на `ICorDebugType` , ссылающийся на первый универсальный <xref:System.Type> параметр конструктора класса, который ссылается этот `ICorDebugType`.|  
|[Метод GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Получает число измерений в тип массива.|  
|[Метод GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Получает указатель интерфейса на ICorDebugValue, содержащий значение статического поля, который ссылается указанное поле токена в указанном кадре стека.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Получает значение CorElementType, описывающее в собственный тип среда CLR <xref:System.Type> ссылается этот `ICorDebugType`.|  
  
## <a name="remarks"></a>Примечания  
 Если тип является универсальным, `ICorDebugClass` представляет типа без экземпляров. `ICorDebugType` Интерфейс представляет экземпляры универсального типа. Например, хэш-таблицы\<K, V > может быть представлена `ICorDebugClass`, тогда как хэш-таблицы\<Int32, String > может быть представлена `ICorDebugType`.  
  
 Неуниверсальные типы представлены оба `ICorDebugClass` и `ICorDebugType`. Последний интерфейс появился в .NET Framework версии 2.0 для создания экземпляров типов.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
