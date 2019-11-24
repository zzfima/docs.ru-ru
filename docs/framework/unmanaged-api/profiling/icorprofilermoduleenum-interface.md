---
title: Интерфейс ICorProfilerModuleEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 5c4efff46c2460ee77f5a8011dc80796ac62a69e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442707"
---
# <a name="icorprofilermoduleenum-interface"></a>Интерфейс ICorProfilerModuleEnum
Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerModuleEnum`.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|Возвращает число управляемых модулей, загруженных в приложение.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|Возвращает заданное число смежных модулей из последовательной коллекции объектов начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorProfilerModuleEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Метод EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
