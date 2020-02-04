---
title: Метод ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865783"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Метод ICorProfilerCallback2::GarbageCollectionStarted
Уведомляет профилировщик кода о начале сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Параметры  
 `cGenerations`  
 окне Общее число записей в массиве `generationCollected`.  
  
 `generationCollected`  
 окне Массив логических значений, которые `true`, если в ходе этой сборки мусора будет собираться поколение, соответствующее индексу массива; в противном случае `false`.  
  
 Массив индексируется по значению перечисления [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , которое указывает на поколение.  
  
 `reason`  
 окне Значение перечисления [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) , указывающее причину принудительной сборки мусора.  
  
## <a name="remarks"></a>Заметки  
 Все обратные вызовы, относящиеся к этой сборке мусора, будут происходить между обратным вызовом `GarbageCollectionStarted` и соответствующим обратным вызовом [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) . Эти обратные вызовы не должны выполняться в одном потоке.  
  
 Профилировщик может быть в безопасности проверять объекты в их исходных расположениях во время обратного вызова `GarbageCollectionStarted`. Сборщик мусора начнет перемещать объекты после возврата из `GarbageCollectionStarted`. После возвращения профилировщика из этого обратного вызова профилировщик должен считать, что все идентификаторы объектов являются недопустимыми, пока не получит ответный вызов `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
