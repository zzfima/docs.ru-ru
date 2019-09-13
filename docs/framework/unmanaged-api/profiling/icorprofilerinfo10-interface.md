---
title: Интерфейс ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 06cce79fbb2b2eb143e77e3c6fda194e47d4f4f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928801"
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
