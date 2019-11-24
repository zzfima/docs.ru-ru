---
title: Интерфейс ICorProfilerThreadEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: b83706176091fd70d48e0f50a0fe5988c876f606
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447617"
---
# <a name="icorprofilerthreadenum-interface"></a>Интерфейс ICorProfilerThreadEnum
Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerThreadEnum`.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-getcount-method.md)|Возвращает число потоков, используемых приложением.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-next-method.md)|Возвращает заданное число смежных потоков из упорядоченной коллекции потоков начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorProfilerThreadEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
