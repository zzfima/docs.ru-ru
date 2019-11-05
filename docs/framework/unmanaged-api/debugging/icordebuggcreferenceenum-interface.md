---
title: Интерфейс ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134636"
---
# <a name="icordebuggcreferenceenum-interface"></a>Интерфейс ICorDebugGCReferenceEnum
Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Возвращает указанное число экземпляров [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) , содержащих сведения об объектах, которые будут собираться сборщиком мусора.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugGCReferenceEnum` реализует интерфейс "ICorDebugEnum".  
  
 Экземпляр `ICorDebugGCReferenceEnum` заполняется экземплярами [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) путем вызова метода [метод ICorDebugProcess5:: енумератегкреференцес](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) . Объекты [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) можно перечислить, вызвав метод [Икордебуггкреференце:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) .  
  
 Объекты [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) в коллекции, заполненной этим методом, представляют три вида объектов:  
  
- Объекты из всех управляемых стеков. Сюда входят динамические ссылки в управляемом коде, а также объекты, созданные средой CLR.  
  
- Объекты из таблицы Handle. Сюда входят строгие ссылки (`HNDTYPE_STRONG` и `HNDTYPE_REFCOUNT`) и статические переменные в модуле.  
  
- Объекты из очереди метода завершения. Очередь метода завершения помещает объекты в корни до запуска метода завершения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
