---
title: Метод ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: 074b0b11a822d2b8bcb9588484557e3e5eba69dd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430192"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Метод ICorProfilerCallback4::ReJITCompilationStarted
Уведомляет профилировщик о том, что JIT-компилятор начал перекомпилировать функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, которая была запущена JIT-компилятором для перекомпиляции.  
  
 `rejitId`  
 окне Идентификатор повторной компиляции новой версии функции.  
  
 `fIsSafeToBlock`  
 [in] `true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения. Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.  
  
## <a name="remarks"></a>Примечания  
 Можно получить более одной пары вызовов методов `ReJITCompilationStarted` и [режиткомпилатионфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов. Например, среда выполнения начинает перекомпилировать метод а, но необходимо запустить конструктор класса для класса B. Таким образом, среда выполнения перекомпилирует конструктор для класса B и запускает его. Пока конструктор выполняется, он вызывает метод а, что вызывает повторную компиляцию метода а. В этом сценарии первая перекомпиляция метода A останавливается. Однако обе попытки перекомпилировать метод а сообщают о событиях JIT-компиляции.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT-компиляции в случаях, когда два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает `ReJITCompilationStarted`; Однако прежде чем поток A вызовет [режиткомпилатионфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback:: ексцептионсеарчфунктионентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `ReJITCompilationStarted` для потока а. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов [режиткомпилатионфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) . Однако в этом случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [Метод ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
