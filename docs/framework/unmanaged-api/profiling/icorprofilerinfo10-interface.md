---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 496959ecac5b16f1faa138aec90c5194d15cb105
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974014"
---
# <a name="icorprofilerinfo10-interface"></a>Интерфейс ICorProfilerInfo10

Подкласс [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) , предоставляющий методы для изменения Il функции, запроса сведений из среды выполнения, а также приостановки и возобновления работы среды выполнения.

## <a name="methods"></a>Методы  

| Метод|Описание|  
| ------------|-----------------|  
|[Метод Енумератеобжектреференцес](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются). |
|[Метод Исфрозенобжект](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|Определяет, находится ли объект в сегменте, доступном только для чтения. |
|[Метод Жетлохобжектсизесрешолд](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Возвращает значение заданного порога LOH. |
|[Метод Рекуестрежитвисинлинерс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| Режитс запрошенные методы, а также любые запрашиваются методы.  |
|[Метод Суспендрунтиме](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| Приостанавливает выполнение среды выполнения без выполнения сборки мусора. |
|[Метод Ресумерунтиме](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| Возобновляет работу среды выполнения без выполнения сборки мусора. |

## <a name="requirements"></a>Требования  
**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
**Заголовок.** CorProf. idl, CorProf. h  
**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 
## <a name="see-also"></a>См. также
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
