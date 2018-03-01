---
title: "Метод ICorProfilerCallback4::SurvivingReferences2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db40e908421c45e9d4192c436995d8137f81ec0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4survivingreferences2-method"></a>Метод ICorProfilerCallback4::SurvivingReferences2
Предоставляет информацию о структуре объектов в куче в результате сборки мусора без сжатия. Этот метод вызывается, если профилировщик реализует [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейса. Этот обратный вызов заменяет [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) метода, так как он может объектах, длина которых превышает нельзя выразить значением типа ULong.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a>Параметры  
 `cSurvivingObjectIDRanges`  
 [in] Количество блоков смежных объектов, оставшихся в результате сборки мусора без сжатия. То есть значение `cSurvivingObjectIDRanges` является размером массивов `objectIDRangeStart` и `cObjectIDRangeLength`, в которых хранятся идентификаторы `ObjectID` и длины каждого блока объектов соответственно.  
  
 Следующие два аргумента `SurvivingReferences2` являются параллельными массивами. Иными словами, `objectIDRangeStart` и `cObjectIDRangeLength` относятся к одному и тому же блоку смежных объектов.  
  
 `objectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является начальным адресом блока смежных активных объектов в памяти.  
  
 `cObjectIDRangeLength`  
 [in] Массив целых чисел, каждое из которых представляет размер оставшегося блока смежных объектов в памяти.  
  
 Размер указывается для каждого блока, ссылка на который имеется в массиве `objectIDRangeStart`.  
  
## <a name="remarks"></a>Примечания  
 Для определения того, уцелел ли объект после сборки мусора, элементы массивов `objectIDRangeStart` и `cObjectIDRangeLength` должны интерпретироваться следующим образом. Предположим, что значение `ObjectID` (`ObjectID`) находится в следующем диапазоне:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 При любом значении `i`, находящемся в указанном ниже диапазоне, объект уцелел после сборки мусора.  
  
 0 <= `i` < `cSurvivingObjectIDRanges`  
  
 Сборка мусора без сжатия освобождает память, занятую "мертвыми" объектами, но не сжимает освобожденное пространство. В результате этого память возвращается в кучу, но активные объекты не перемещаются.  
  
 Среда CLR вызывает метод `SurvivingReferences2` для выполнения сборки мусора без сжатия. Для мусора со сжатием [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) вызывается. Отдельная операция сборки мусора может предусматривать сжатие для одного поколения и не предусматривать — для другого. Для сборки мусора для любого конкретного поколения, профилировщик получит либо `SurvivingReferences2` обратного вызова или [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) обратного вызова, но не оба.  
  
 Несколько обратных вызовов `SurvivingReferences2` может быть получено в ходе определенной сборки мусора из-за ограниченной внутренней буферизации, нескольких обратных вызовов во время сборки мусора на сервере и по другим причинам. При получении нескольких обратных вызовов во время сборки мусора информация накапливается — все ссылки, сообщаемые в обратных вызовах `SurvivingReferences2`, сохранятся после сборки мусора.  
  
 Если профилировщик реализует оба [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) и [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейсы, `SurvivingReferences2` метод вызывается перед [ICorProfilerCallback2:: SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) метода, но только если `SurvivingReferences2` возвращает успешно. Профилировщики могут возвращать значение HRESULT, указывающее на сбой метода `SurvivingReferences2`, что позволяет избежать вызова второго метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
