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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865198"
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
  
## <a name="remarks"></a>Заметки  
 Можно получить более одной пары вызовов методов `ReJITCompilationStarted` и [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов. Например, среда выполнения начинает перекомпилировать метод а, но необходимо запустить конструктор класса для класса B. Таким образом, среда выполнения перекомпилирует конструктор для класса B и запускает его. Пока конструктор выполняется, он вызывает метод а, что вызывает повторную компиляцию метода а. В этом сценарии первая перекомпиляция метода A останавливается. Однако обе попытки перекомпилировать метод а сообщают о событиях JIT-компиляции.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT-компиляции в случаях, когда два потока одновременно осуществляют обратные вызовы. Например, поток A вызывает `ReJITCompilationStarted`; Однако прежде чем поток A вызовет [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает метод [ICorProfilerCallback:: ексцептионсеарчфунктионентер](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `ReJITCompilationStarted` для потока а. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов [режиткомпилатионфинишед](icorprofilercallback4-rejitcompilationfinished-method.md) . Однако в этом случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Метод ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
