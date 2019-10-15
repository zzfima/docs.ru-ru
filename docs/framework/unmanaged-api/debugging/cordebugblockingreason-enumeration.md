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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fcf160b3e3b2b238520e3db5ba2e74b270380a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274132"
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`BLOCKING_NONE`|Только для внутреннего использования.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Поток пытается получить критическую секцию, связанную с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> методов <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> или.|  
|`BLOCKING_MONITOR_EVENT`|Поток ожидает события, связанного с блокировкой монитора для объекта. Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` методов.|  
  
## <a name="remarks"></a>Примечания  
 Если элемент `BLOCKING_MONITOR_CRITICAL_SECTION` или `BLOCKING_MONITOR_EVENT` используется в структуре [CorDebugBlockingObject](cordebugblockingobject-structure.md), элемент `pBlockingObject` структуры указывает на интерфейс "ICorDebugValue", представляющий объект, который необходимо указать. Также гарантируется реализация интерфейса [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
- [Отладка](index.md)
