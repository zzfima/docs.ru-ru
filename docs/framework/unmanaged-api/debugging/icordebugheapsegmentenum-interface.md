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
ms.openlocfilehash: 98e3351c9c86961d11b0985117259d0ff3b609ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794418"
---
# <a name="icordebugheapsegmentenum-interface"></a>Интерфейс ICorDebugHeapSegmentEnum
Предоставляет перечислитель для областей памяти управляемой кучи. Этот интерфейс является подклассом интерфейса ICorDebugEnum.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](icordebugheapsegmentenum-next-method.md)|Возвращает указанное число экземпляров [COR_HEAPOBJECT](cor-heapobject-structure.md) , содержащих сведения о регионах управляемой кучи.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugHeapSegmentEnum` реализует интерфейс ICorDebugEnum.  
  
 Экземпляр `ICorDebugHeapSegmentEnum` заполняется [COR_HEAPOBJECT](cor-heapobject-structure.md) экземплярами путем вызова метода [метод ICorDebugProcess5:: енумератехеапрегионс](icordebugprocess5-enumerateheapregions-method.md) . Объекты [COR_HEAPOBJECT](cor-heapobject-structure.md) в коллекции можно перечислить, вызвав метод [Икордебугхеапсегментенум:: Next](icordebugheapsegmentenum-next-method.md) .  
  
 Объект `ICorDebugHeapSegmentEnum` Collection перечисляет все области памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах. Он может включать сведения о пустых или зарезервированных регионах памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
