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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83caaa04481b4ed92407294584512b38553710b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501492"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Метод ICorProfilerCallback4::ReJITCompilationStarted
Уведомляет профилировщик о начале повторной компиляции функции компилятор just-in-time (JIT).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, JIT-компилятор начал перекомпилировать.  
  
 `rejitId`  
 [in] Повторная компиляция идентификатор новой версии функции.  
  
 `fIsSafeToBlock`  
 [in] `true` для указания, что блокировок может вызвать среды выполнения для вызывающего потока для возврата из этого обратного вызова; `false` для указания, что блокировка не повлияет на работу среды выполнения. Значение `true` не повреждает среды выполнения, но могут повлиять на результаты профилирования.  
  
## <a name="remarks"></a>Примечания  
 Возможно, для получения более чем одну пару `ReJITCompilationStarted` и [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) метод вызывает для каждой функции из-за способа выполнения конструкторы класса дескрипторов. Например среда выполнения начинает перекомпилировать метод A, но конструктор класса для класса B нужно выполнить. Таким образом среда выполнения повторных компиляций конструктор для класса B и запускает его. Во время работы конструктора, он делает вызов метода А, который вызывает метод A попытку повторной компиляции. В этом случае первый перекомпиляция метод A будет прерван. Тем не менее оба пытается перекомпилировать метод являются сообщил с события перекомпиляции JIT-компилятора.  
  
 Профилировщики должны поддерживать последовательность обратных вызовов для перекомпиляции JIT в случаях, где два потока одновременно осуществляют обратных вызовов. Например, поток A вызывает `ReJITCompilationStarted`; тем не менее, прежде чем поток A вызывает [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) с ИД функции из `ReJITCompilationStarted` обратного вызова для потока A. Может показаться, что идентификатор функции должно находиться допустимым так как вызов [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) еще не получил профилировщиком. Однако в этом случае идентификатор функции недопустим.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [Метод JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [Метод ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
