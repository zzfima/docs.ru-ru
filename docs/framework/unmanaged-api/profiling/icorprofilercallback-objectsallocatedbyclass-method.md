---
title: Метод ICorProfilerCallback::ObjectsAllocatedByClass
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 028207486f43e35086ed2e515eb3ae6bca304491
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866082"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Метод ICorProfilerCallback::ObjectsAllocatedByClass
Уведомляет профилировщик о количестве экземпляров каждого указанного класса, созданных с момента последнего сбора мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `cClassCount`  
 окне Размер массивов `classIds` и `cObjects`.  
  
 `classIds`  
 окне Массив идентификаторов классов, где каждый идентификатор указывает класс с одним или несколькими экземплярами.  
  
 `cObjects`  
 окне Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в массиве `classIds`.  
  
## <a name="remarks"></a>Заметки  
 Массивы `classIds` и `cObjects` являются параллельными массивами. Например, `classIds[i]` и `cObjects[i]` ссылаются на один и тот же класс. Если с момента предыдущего сбора мусора экземпляр класса не был создан, класс опускается. Обратный вызов `ObjectsAllocatedByClass` не будет сообщать объекты, выделенные в куче больших объектов.  
  
 Числа, сообщаемые `ObjectsAllocatedByClass`, являются только оценками. Для точного числа счетчиков используйте параметр [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).  
  
 Массив `classIds` может содержать одну или несколько записей null, если в соответствующем массиве `cObjects` имеются типы, выгрузка которых выполняется.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
