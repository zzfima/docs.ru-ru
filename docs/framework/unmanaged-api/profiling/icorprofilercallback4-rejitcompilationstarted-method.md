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
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177083"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>Метод ICorProfilerCallback4::ReJITCompilationStarted
Уведомляет профайлера о том, что компилятор JIT(IIT) начал перекомпилировать функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 (в) Идентификатор функции, которую начал пересоставлять компилятор JIT.  
  
 `rejitId`  
 (в) Идентификатор перекомпиляции новой версии функции.  
  
 `fIsSafeToBlock`  
 (в) `true` указать, что блокировка может привести к тому, что время выполнения может привести к тому, что поток вызова вернется из этого обратного вызова; `false` указать, что блокировка не повлияет на работу времени выполнения. Значение `true` не наносит ущерба времени выполнения, но может повлиять на результаты профилирования.  
  
## <a name="remarks"></a>Remarks  
 Можно получить более одной пары `ReJITCompilationStarted` и [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) метод требует для каждой функции из-за того, как время выполнения обрабатывает конструкторов класса. Например, время выполнения начинает перекомпилировать метод A, но необходимо запустить конструктор класса для класса B. Таким образом, время выполнения перекомпилирует конструктор для класса B и запускает его. Во время работы конструктора он вызывает метод А, который приводит к повторному компилированию метода А. В этом сценарии первая перекомпиляция метода А останавливается. Однако обе попытки перекомпилировать метод А сообщаются с событиями перекомпиляции JIT.  
  
 Профилеры должны поддерживать последовательность обратных вызовов перекомпийки JIT в тех случаях, когда два потока одновременно делают обратные вызовы. Например, вызовы `ReJITCompilationStarted`потока А; однако, прежде чем поток A вызывает [ReJITCompilationFinished,](icorprofilercallback4-rejitcompilationfinished-method.md)поток B вызывает [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) с идентификатором функции от `ReJITCompilationStarted` обратного вызова для потока A. Может показаться, что идентификатор функции еще не должен быть действительным, поскольку вызов [в ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) еще не был получен профайлером. Однако в этом случае идентификатор функции действителен.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
- [Метод ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
