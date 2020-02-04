---
title: Метод ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866511"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>Метод ICorProfilerCallback::ExceptionCatcherEnter
Уведомляет профилировщик, что управление передается соответствующему блоку `catch`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Параметры

- `functionId`

  \[в] идентификатор функции, содержащей блок `catch`.
  
- `objectId`

  \[в] идентификатор обрабатываемого исключения.

## <a name="remarks"></a>Заметки  
 Метод `ExceptionCatcherEnter` вызывается, только если точка перехвата находится в коде, скомпилированном в JIT-компиляторе. Исключение, перехваченное в неуправляемом коде или во внутреннем коде среды выполнения, не будет вызывать это уведомление. Значение `objectId` передается снова, так как сборщик мусора мог переместить объект с момента `ExceptionThrown` уведомления.  
  
 Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора. Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.  
  
 Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)
