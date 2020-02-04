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
ms.openlocfilehash: 2713fa90240cb0bf41f455b6ed65d76c568a2cf8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868269"
---
# <a name="icorprofilermoduleenum-interface"></a>Интерфейс ICorProfilerModuleEnum
Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icorprofilermoduleenum-clone-method.md)|Получает указатель на копию этого интерфейса `ICorProfilerModuleEnum`.|  
|[Метод GetCount](icorprofilermoduleenum-getcount-method.md)|Возвращает число управляемых модулей, загруженных в приложение.|  
|[Метод Next](icorprofilermoduleenum-next-method.md)|Возвращает заданное число смежных модулей из последовательной коллекции объектов начиная с текущей позиции перечислителя в последовательности.|  
|[Метод Reset](icorprofilermoduleenum-reset-method.md)|Перемещает курсор перечислителя в начальную позицию последовательности.|  
|[Метод Skip](icorprofilermoduleenum-skip-method.md)|Перемещает курсор перечислителя из текущей позиции, пропуская указанное число элементов.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorProfilerModuleEnum` является перечислителем. Он позволяет получающему массив объекту запрашивать элементы у отправляющего объекта с приемлемой для себя скоростью. Иными словами, получающий объект может явным образом управлять потоком элементов массива, избегая тем самым проблем, связанных с передачей больших массивов в качестве параметров метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейсы профилирования](profiling-interfaces.md)
- [Метод EnumModules](icorprofilerinfo3-enummodules-method.md)
