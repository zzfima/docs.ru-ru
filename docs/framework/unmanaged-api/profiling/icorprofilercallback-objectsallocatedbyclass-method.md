---
title: "Метод ICorProfilerCallback::ObjectsAllocatedByClass"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28c0ff537a5b2133bdeb1db8aeadf5545d8dfd0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
 [in] Массив целых чисел, где каждое целое число задает количество экземпляров для классом-аналогом в `classIds` массива.  
  
## <a name="remarks"></a>Примечания  
 `classIds` И `cObjects` массивы являются параллельными массивами. Например `classIds[i]` и `cObjects[i]` ссылаются на том же классе. Если с момента предыдущей сборки мусора будет создан экземпляр класса, класс пропускается. `ObjectsAllocatedByClass` Обратного вызова не будут передавать объектов, помещенных в кучу больших объектов.  
  
 Сообщаемые номера `ObjectsAllocatedByClass` представляют собой только оценки. Точное количество использовать [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).  
  
 `classIds` Массив может содержать один или несколько элементы со значением null, если соответствующий `cObjects` массив содержит типы, которые выгрузки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
