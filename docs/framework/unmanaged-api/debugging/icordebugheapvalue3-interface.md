---
title: Интерфейс ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24747ccea37707a474d8fff7844ee07301b8194a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914890"
---
# <a name="icordebugheapvalue3-interface"></a>Интерфейс ICorDebugHeapValue3
Предоставляет свойства блокировки монитора объектов. Этот интерфейс расширяет интерфейсы ICorDebugHeapValue и ICorDebugHeapValue2.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetThreadOwningMonitorLock](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|Возвращает управляемый поток, которому принадлежит блокировка монитора для этого объекта.|  
|[Метод GetMonitorEventWaitList](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|Предоставляет упорядоченный список потоков, поставленных в очередь на событие, связанное с блокировкой монитора.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
