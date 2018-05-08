---
title: ICorDebugType интерфейс1
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
ms.openlocfilehash: de2871b406bb9da84d20d7c526ad4a703baae409
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugtype-interface1"></a>ICorDebugType интерфейс1
Представляет тип, либо простой или сложной (который определяемый пользователем). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Получает указатель интерфейса на ICorDebugTypeEnum, который ссылается на параметр универсального <xref:System.Type> параметры типа класса, который ссылается этот `ICorDebugType`.|  
|[Метод GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Возвращает указатель интерфейса `ICorDebugType` , ссылается на базовый класс для класса, который ссылается этот `ICorDebugType`, если он существует.|  
|[Метод GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Получает указатель интерфейса на ICorDebugClass, который ссылается на типизированный конструктор `ICorDebugType`.|  
|[Метод GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Возвращает указатель интерфейса `ICorDebugType` , ссылается на первый универсальный <xref:System.Type> параметра для конструктора класса, упоминаемой в этом `ICorDebugType`.|  
|[Метод GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Возвращает число измерений в тип массива.|  
|[Метод GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Возвращает указатель на интерфейс ICorDebugValue, содержащий значение статического поля, который ссылается указанное поле токена в указанном кадре стека.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Возвращает значение CorElementType, которое описывает собственный тип общеязыковая среда выполнения <xref:System.Type> ссылается этот `ICorDebugType`.|  
  
## <a name="remarks"></a>Примечания  
 Если тип является универсальным, `ICorDebugClass` представляет типа без экземпляров. `ICorDebugType` Интерфейс представляет экземпляр универсального типа. Например, хэш-таблицы\<K, V > может быть представлена `ICorDebugClass`, тогда как хэш-таблицы\<Int32, String > будут представлены в `ICorDebugType`.  
  
 Неуниверсальные типы представлены как `ICorDebugClass` и `ICorDebugType`. Последний интерфейс впервые появился в .NET Framework версии 2.0 для создания экземпляров типов.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
