---
title: Метод ICorProfilerCallback4::ReJITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: e010a49dabd3b44602136e70b4c5524a68bdd9e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865211"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>Метод ICorProfilerCallback4::ReJITCompilationFinished
Уведомляет профилировщик о том, что JIT-компилятор завершил повторную компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор перекомпилированной функции.  
  
 `rejitId`  
 [in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.  
  
 `hrStatus`  
 окне Значение, указывающее, успешно ли выполнена повторная компиляция JIT.  
  
 `fIsSafeToBlock`  
 [in] `true`, чтобы указать, что блокировка может привести к ожиданию средой выполнения вызывающего потока от этого обратного вызова. `false`, чтобы указать, что блокировка не повлияет на работу среды выполнения.  
  
 Значение `true` не нанесет вред исполняющей среде, но может повлиять на результаты профилирования.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
- [Метод ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)
