---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175074"
---
# <a name="icorprofilerinfo10-interface"></a>Интерфейс ICorProfilerInfo10

Подкласс [ICorProfilerInfo9,](icorprofilerinfo9-interface.md) который предоставляет методы для изменения функции IL, информации запроса из времени выполнения, а также приостановить и возобновить время выполнения.

## <a name="methods"></a>Методы  

| Метод|Описание|  
| ------------|-----------------|  
|[Метод EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|С учетом ObjectID, обратный вызов и clientData перечисляет ссылку на каждый объект (если таковой имеется). |
|[Метод IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Учитывая ObjectID, определяет, находится ли объект в сегменте только для чтения. |
|[Метод GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Получает значение настроенного порога LOH. |
|[Метод RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| Перекладывает запрошенные методы, а также любые inliners из запрошенных методов.  |
|[Метод SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Приостанавливает время выполнения без выполнения GC. |
|[Метод ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Возобновляет время выполнения без выполнения GC. |

## <a name="requirements"></a>Требования  
**Платформы:** Смотрите [операционные системы, поддерживаемые .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)  
**Заголовок:** CorProf.idl, CorProf.h  
**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
