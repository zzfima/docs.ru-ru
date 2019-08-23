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
ms.openlocfilehash: b830af5d59c0eb177d815451ecedbdc14121aaad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964759"
---
# <a name="icordebugtype-interface"></a>Интерфейс ICorDebugType
Представляет тип — базовый или сложный (то есть определяемый пользователем). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Возвращает указатель интерфейса на ICorDebugTypeEnum, который ссылается на универсальные <xref:System.Type> параметры класса, на который ссылается this `ICorDebugType`.|  
|[Метод GetBase](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на базовый класс класса, на который ссылается этот `ICorDebugType`класс, если он существует.|  
|[Метод GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Возвращает указатель интерфейса на объект ICorDebugClass, который ссылается на типизированный конструктор этого `ICorDebugType`объекта.|  
|[Метод GetFirstTypeParameter](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Возвращает указатель интерфейса на объект `ICorDebugType` , который ссылается на первый универсальный <xref:System.Type> параметр для конструктора класса, на который ссылается this. `ICorDebugType`|  
|[Метод GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Возвращает число измерений в типе массива.|  
|[Метод GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Возвращает указатель интерфейса на объект ICorDebugValue, содержащий значение статического поля, на которое ссылается заданный токен поля в указанном кадре стека.|  
|[Метод GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Возвращает значение корелементтипе, описывающее собственный тип среды <xref:System.Type> CLR, на который ссылается this. `ICorDebugType`|  
  
## <a name="remarks"></a>Примечания  
 Если тип является универсальным, `ICorDebugClass` представляет тип, не являющийся экземпляром. `ICorDebugType` Интерфейс представляет экземпляр универсального типа. Например, таблица Hashtable\<K, V > будет представлена в `ICorDebugClass`, тогда как Hashtable\< `ICorDebugType`Int32, String > будет представлена.  
  
 Типы, не являющиеся универсальными, представлены `ICorDebugClass` как `ICorDebugType`, так и. Последний интерфейс появился в .NET Framework версии 2,0 для обработки создания экземпляра типа.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
