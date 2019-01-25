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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c610445d5467a49b8a50b279d8f7fe706e21f73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555665"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Метод ICorProfilerCallback2::GarbageCollectionStarted
Уведомляет профилировщик кода, что сборка мусора была начата.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cGenerations`  
 [in] Общее число записей в `generationCollected` массива.  
  
 `generationCollected`  
 [in] Массив логических значений, которые являются `true` если поколение, соответствующий индекс массива, собирая их с этой сборке мусора, в противном случае — `false`.  
  
 Массив индексируется по значение [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) перечисления, которое задает поколение.  
  
 `reason`  
 [in] Значение [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) вызывалась перечисления, указывающее причину сборки мусора.  
  
## <a name="remarks"></a>Примечания  
 Все обратные вызовы, которые относятся к этой сборке мусора происходит между `GarbageCollectionStarted` обратного вызова и соответствующий [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) обратного вызова. Эти обратные вызовы должны осуществляться в одном потоке.  
  
 Безопасно для профилировщика для проверки объектов в исходном расположении во время `GarbageCollectionStarted` обратного вызова. Сборщик мусора начнется перемещение объектов после возврата из `GarbageCollectionStarted`. После возврата из этого обратного вызова профилировщика, профилировщик следует учитывать все идентификаторы объектов к недействительности, пока не получит `ICorProfilerCallback2::GarbageCollectionFinished` обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
