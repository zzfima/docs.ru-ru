---
title: Метод ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 96ab77a36c0a0bddda0fca342433666dd19082d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426192"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>Метод ICorProfilerCallback::JITCompilationStarted
Уведомляет профилировщик, что компилятор just-in-time (JIT) начал компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой начинается компиляция.  
  
 `fIsSafeToBlock`  
 окне Значение, указывающее профилировщику, будет ли блокировка влиять на работу среды выполнения. Значение `true`, если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. в противном случае `false`.  
  
 Хотя значение `true` не будет нанести вред среде выполнения, оно может исказить результаты профилирования.  
  
## <a name="remarks"></a>Заметки  
 Можно получить более одной пары `JITCompilationStarted` и [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) для каждой функции, так как среда выполнения обрабатывает конструкторы классов. Например, среда выполнения начинает JIT-компилировать метод а, но необходимо запустить конструктор класса B. Поэтому среда выполнения JIT компилирует конструктор для класса B и запускает его. Пока конструктор выполняется, он вызывает метод а, что вызывает повторную JIT-компиляцию метода. В этом сценарии первая JIT-компиляция метода A останавливается. Однако обе попытки JIT-компиляции метода A сообщаются с событиями JIT-компиляции. Если профилировщик будет заменять код промежуточного языка MSIL для метода а путем вызова метода [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) , он должен сделать это для обоих событий `JITCompilationStarted`, но может использовать один и тот же блок MSIL для обоих.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов JIT в случаях, когда два потока одновременно осуществляют обратные вызовы. Например, поток а вызывает `JITCompilationStarted`. Однако до того, как поток A вызовет `JITCompilationFinished`, поток B вызывает [ICorProfilerCallback:: ексцептионсеарчфунктионентер](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции из обратного вызова `JITCompilationStarted` потока A. Может показаться, что идентификатор функции еще не должен быть допустимым, поскольку профилировщик еще не получил вызов `JITCompilationFinished`. Однако в таком случае идентификатор функции является допустимым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
