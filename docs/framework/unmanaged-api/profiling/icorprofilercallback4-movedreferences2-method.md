---
title: "Метод ICorProfilerCallback4::MovedReferences2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.MovedReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8137d944081475095509150cce84a611b7030eb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4movedreferences2-method"></a>Метод ICorProfilerCallback4::MovedReferences2
Вызывается для предоставления сведений о новой структуре объектов в куче в результате сжатия сборки мусора. Этот метод вызывается, если профилировщик реализует [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейса. Этот обратный вызов заменяет [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) метода, так как он может объектах, длина которых превышает нельзя выразить значением типа ULong.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a>Параметры  
 `cMovedObjectIDRanges`  
 [in] Количество блоков смежных объектов, перемещенных в результате сжатия сборки мусора. Таким образом значение `cMovedObjectIDRanges` представляет общий размер массивов `oldObjectIDRangeStart`, `newObjectIDRangeStart` и `cObjectIDRangeLength`.  
  
 Следующие три аргумента `MovedReferences2` являются параллельными массивами. Другими словами, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` и `cObjectIDRangeLength[i]` относятся к одному и тому же блоку смежных объектов.  
  
 `oldObjectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является старым (до сборки мусора) начальным адресом блока смежных активных объектов в памяти.  
  
 `newObjectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является новым (после сборки мусора) начальным адресом блока смежных активных объектов в памяти.  
  
 `cObjectIDRangeLength`  
 [in] Массив целых чисел, каждое из которых представляет размер блока смежных объектов в памяти.  
  
 Размер указывается для каждого блока, ссылка на который имеется в массивах `oldObjectIDRangeStart` и `newObjectIDRangeStart`.  
  
## <a name="remarks"></a>Примечания  
 Сжатие сборки мусора без сжатия освобождает память, занятую "мертвыми" объектами, и сжимает это освобожденное пространство. В результате динамические объекты могут быть перемещены в кучу, и значения `ObjectID`, распространенные предыдущими уведомлениями, могут измениться.  
  
 Предположим, что существующее значение `ObjectID` (`oldObjectID`) находится в следующем диапазоне:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 В этом случае смещение от начала диапазона к началу объекта следующее:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Для любого значения параметра `i`, который находится в следующем диапазоне:  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 можно вычислить новый `ObjectID` следующим образом:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 Ни одно из значений `ObjectID`, переданных `MovedReferences2`, не является допустимым во время самого обратного вызова, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `MovedReferences2`. Объект [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) обратного вызова указывает, что все объекты были перемещены в новые расположения и можно выполнять проверку.  
  
 Если профилировщик реализует оба [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) и [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) интерфейсы, `MovedReferences2` метод вызывается перед [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) метода, но только если `MovedReferences2` метод возвращает успешно. Профилировщики могут возвращать значение HRESULT, указывающее на сбой в методе `MovedReferences2`, что позволяет избежать вызова второго метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
