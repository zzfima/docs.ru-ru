---
title: Интерфейс ICorProfilerObjectEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: 95dce47a65bd437525011d2c1588d7e13adac85b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428182"
---
# <a name="icorprofilerobjectenum-interface"></a>Интерфейс ICorProfilerObjectEnum
Предоставляет методы для последовательного прохода по коллекции зафиксированных объектов, создаваемых программой [Ngen. exe (генератор образов в машинном код)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerObjectEnum`.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|Возвращает общее число замороженных объектов в коллекции.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|Перемещает курсор этого перечислителя из текущей позиции, чтобы было пропущено указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Интерфейс `ICorProfilerObjectEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получатель может явно управлять потоком элементов массива, тем самым избегая проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
 Используйте [ICorProfilerInfo2:: EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) для получения указателя на интерфейс `ICorProfilerObjectEnum`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Метод EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
