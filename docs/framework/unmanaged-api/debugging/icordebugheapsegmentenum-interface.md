---
title: Интерфейс ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138453"
---
# <a name="icordebugheapsegmentenum-interface"></a>Интерфейс ICorDebugHeapSegmentEnum
Предоставляет перечислитель для областей памяти управляемой кучи. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Возвращает указанное число экземпляров [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) , содержащих сведения о регионах управляемой кучи.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugHeapSegmentEnum` реализует интерфейс ICorDebugEnum.  
  
 Экземпляр `ICorDebugHeapSegmentEnum` заполняется экземплярами [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) путем вызова метода [метод ICorDebugProcess5:: енумератехеапрегионс](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) . Объекты [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапсегментенум:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .  
  
 Объект `ICorDebugHeapSegmentEnum` Collection перечисляет все области памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Он может включать сведения о пустых или зарезервированных регионах памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
