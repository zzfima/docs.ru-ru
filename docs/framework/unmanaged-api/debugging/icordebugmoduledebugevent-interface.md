---
title: Интерфейс ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792900"
---
# <a name="icordebugmoduledebugevent-interface"></a>Интерфейс ICorDebugModuleDebugEvent
Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetModule](icordebugmoduledebugevent-getmodule-method.md)|Возвращает объединенный модуль, который только что был загружен или выгружен.|  
  
## <a name="remarks"></a>Заметки  
 Типы событий [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) и [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) реализуют этот интерфейс.  
  
> [!NOTE]
> Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
