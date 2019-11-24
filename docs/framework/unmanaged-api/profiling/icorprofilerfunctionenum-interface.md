---
title: Интерфейс ICorProfilerFunctionEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 17f7243096b7ac18e456f8f31196055492015346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447798"
---
# <a name="icorprofilerfunctionenum-interface"></a>Интерфейс ICorProfilerFunctionEnum
Предоставляет методы для последовательного перебора коллекции функций в среде CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerFunctionEnum`.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|Возвращает заданное число смежных функций из последовательной коллекции функций начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorProfilerFunctionEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
 Интерфейс `ICorProfilerFunctionEnum` перечисляет функции, которые уже были скомпилированы для JIT-отладки, но не включает функции, загруженные из собственных образов, созданных с помощью программы Ngen.exe.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Метод EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
