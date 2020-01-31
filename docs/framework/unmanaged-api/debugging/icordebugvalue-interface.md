---
title: Интерфейс ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791135"
---
# <a name="icordebugvalue-interface"></a>Интерфейс ICorDebugValue
Представляет значение в отлаживаемом процессе. Значением может быть значение Read или Write.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Этот метод в настоящее время не реализован.|  
|[Метод GetAddress](icordebugvalue-getaddress-method.md)|Возвращает адрес этого `ICorDebugValue` объекта, который находится в процессе отладки.|  
|[Метод GetSize](icordebugvalue-getsize-method.md)|Возвращает размер данного объекта `ICorDebugValue` в байтах.|  
|[Метод GetType](icordebugvalue-gettype-method.md)|Возвращает тип примитива данного объекта `ICorDebugValue`.|  
  
## <a name="remarks"></a>Заметки  
 В общем случае владение объектом значения передается при его возврате. Получатель отвечает за удаление ссылки из объекта после завершения работы с объектом.  
  
 В зависимости от того, откуда было получено значение, оно может остаться недействительным после возобновления процесса. Поэтому в общем случае значение не должно удерживаться в вызове метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
