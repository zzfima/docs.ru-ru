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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1200ca14b91c101a8145a3aed8023002ddb9298b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746639"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>Метод ICorProfilerCallback::ObjectsAllocatedByClass
Уведомляет профилировщик о количестве экземпляров каждого заданного класса, которые были созданы после последней сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>Параметры  
 `cClassCount`  
 [in] Размер `classIds` и `cObjects` массивов.  
  
 `classIds`  
 [in] Массив идентификаторов класса, где каждый идентификатор определяет класс с одним или несколькими экземплярами.  
  
 `cObjects`  
 [in] Массив целых чисел, где каждое целое число указывает количество экземпляров для соответствующего класса в `classIds` массива.  
  
## <a name="remarks"></a>Примечания  
 `classIds` И `cObjects` массивы являются параллельными массивами. Например `classIds[i]` и `cObjects[i]` ссылаться на тот же класс. Если с момента предыдущей сборки мусора был создан экземпляр класса, класс пропускается. `ObjectsAllocatedByClass` Обратный вызов не будет выдавать объектов, помещенных в кучу больших объектов.  
  
 Сообщаемое номера `ObjectsAllocatedByClass` только приблизительные. Для точного подсчета строк, используйте [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 `classIds` Массив может содержать один или несколько записи со значением null, если соответствующий `cObjects` массив содержит типы, которые выгрузки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
