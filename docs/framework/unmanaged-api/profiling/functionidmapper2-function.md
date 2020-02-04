---
title: Функция FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: af0ef412395394bb660ae6ed64fb154caef41655
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866922"
---
# <a name="functionidmapper2-function"></a>Функция FunctionIDMapper2
Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в ответных вызовах [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), [FunctionTailcall3](functiontailcall3-function.md)или[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) для этой функции. `FunctionIDMapper2` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcId`

  \[в] идентификатор функции для повторного сопоставления.

- `clientData`

  \[в] указатель на данные, которые используются для однозначного определения между средами выполнения.

- `pbHookFunction`

  \[out] указатель на значение, которое задается профилировщику для `true`, если требуется получить `FunctionEnter3`, `FunctionLeave3`и `FunctionTailcall3`, а также обратные вызовы `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`и `FunctionTailcall3WithInfo`. в противном случае это значение задается как `false`.

## <a name="return-value"></a>Возвращаемое значение  
 Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции. Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`. В противном случае возвращаемое значение null приводит к непредсказуемым результатам, включая возможное прерывание процесса.  
  
## <a name="remarks"></a>Заметки  
 Этот метод расширяет функцию [FunctionIDMapper](functionidmapper-function.md) с помощью дополнительного параметра, который используется для передачи данных клиента. Эти данные клиента служат для однозначного определения среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [ICorProfilerInfo3::SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
