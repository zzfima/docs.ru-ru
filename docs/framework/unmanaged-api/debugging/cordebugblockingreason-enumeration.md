---
title: Перечисление CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: bc488e55bf64468eb62e2dc6eaedca62ebde3310
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098990"
---
# <a name="cordebugblockingreason-enumeration"></a>Перечисление CorDebugBlockingReason
Указывает возможные причины блокировки потока на данном объекте.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`BLOCKING_NONE`|Только для внутреннего использования.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Поток пытается получить критическую секцию, связанную с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из методов <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> или <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>.|  
|`BLOCKING_MONITOR_EVENT`|Поток ожидает события, связанного с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из методов <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait`.|  
  
## <a name="remarks"></a>Заметки  
 Если в структуре [CorDebugBlockingObject](cordebugblockingobject-structure.md) используется элемент `BLOCKING_MONITOR_CRITICAL_SECTION` или `BLOCKING_MONITOR_EVENT`, `pBlockingObject` элемент структуры указывает на интерфейс "ICorDebugValue", представляющий объект, который необходимо указать. Также гарантируется реализация интерфейса [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
