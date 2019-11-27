---
title: Метод ICorProfilerCallback::MovedReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
ms.openlocfilehash: d78e7e863ab953182ea7c1ff342593b4bdf3215d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445871"
---
# <a name="icorprofilercallbackmovedreferences-method"></a>Метод ICorProfilerCallback::MovedReferences
Вызывается для предоставления сведений о структуре объектов в куче в результате сжатия сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Параметры  
 `cMovedObjectIDRanges`  
 [in] Количество блоков смежных объектов, перемещенных в результате сжатия сборки мусора. Таким образом значение `cMovedObjectIDRanges` представляет общий размер массивов `oldObjectIDRangeStart`, `newObjectIDRangeStart` и `cObjectIDRangeLength`.  
  
 Следующие три аргумента `MovedReferences` являются параллельными массивами. Другими словами, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` и `cObjectIDRangeLength[i]` относятся к одному и тому же блоку смежных объектов.  
  
 `oldObjectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является старым (до сборки мусора) начальным адресом блока смежных активных объектов в памяти.  
  
 `newObjectIDRangeStart`  
 [in] Массив значений `ObjectID`, каждое из которых является новым (после сборки мусора) начальным адресом блока смежных активных объектов в памяти.  
  
 `cObjectIDRangeLength`  
 [in] Массив целых чисел, каждое из которых представляет размер блока смежных объектов в памяти.  
  
 Размер указывается для каждого блока, ссылка на который имеется в массивах `oldObjectIDRangeStart` и `newObjectIDRangeStart`.  
  
## <a name="remarks"></a>Заметки  
  
> [!IMPORTANT]
> Этот метод сообщает размеры как `MAX_ULONG` для объектов с размером более 4 Гб на 64-разрядных платформах. Чтобы получить размер объектов, превышающих 4 ГБ, используйте вместо этого метод [ICorProfilerCallback4:: MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) .  
  
 Сжатие сборки мусора без сжатия освобождает память, занятую "мертвыми" объектами, и сжимает это освобожденное пространство. В результате динамические объекты могут быть перемещены в кучу, и значения `ObjectID`, распространенные предыдущими уведомлениями, могут измениться.  
  
 Предположим, что существующее значение `ObjectID` (`oldObjectID`) находится в следующем диапазоне:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 В этом случае смещение от начала диапазона к началу объекта следующее:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Для любого значения параметра `i`, который находится в следующем диапазоне:  
  
 0 < = `i` < `cMovedObjectIDRanges`  
  
 можно вычислить новый `ObjectID` следующим образом:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` — `oldObjectIDRangeStart[i]`)  
  
 Ни одно из значений `ObjectID`, переданных `MovedReferences`, не является допустимым во время самого обратного вызова, потому что сборка мусора может находиться в процессе перемещения объектов из старого в новое расположение. В связи с этим профилировщикам не следует пытаться проверять объекты во время вызова `MovedReferences`. Обратный вызов [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) указывает, что все объекты были перемещены в новые расположения, и проверку можно выполнить.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
