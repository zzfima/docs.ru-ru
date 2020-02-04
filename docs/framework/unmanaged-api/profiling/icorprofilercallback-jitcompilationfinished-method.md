---
title: Метод ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: f1cfef464569b577923fbb16624c99358998d29c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866251"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>Метод ICorProfilerCallback::JITCompilationFinished
Уведомляет профилировщик о том, что JIT-компилятор завершил компиляцию функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор скомпилированной функции.

- `hrStatus`

  \[в] значение, указывающее, успешно ли выполнена компиляция.

- `fIsSafeToBlock`

  \[в] значение, указывающее профилировщику на то, что блокировка повлияет на работу среды выполнения. Значение `true`, если блокировка может привести к тому, что среда выполнения будет ожидать возврата вызывающим потоком из этого обратного вызова. в противном случае `false`.

  Хотя значение `true` не будет нанести вред среде выполнения, оно может исказить результаты профилирования.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
