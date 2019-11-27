---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449839"
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
**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Заголовок:** CorProf.idl, CorProf.h  
**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
