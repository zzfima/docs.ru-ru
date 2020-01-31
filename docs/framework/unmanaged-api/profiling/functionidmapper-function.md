---
title: Функция FunctionIDMapper
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866948"
---
# <a name="functionidmapper-function"></a>Функция FunctionIDMapper
Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md) для этой функции. `FunctionIDMapper` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcId`

  \[в] идентификатор функции для повторного сопоставления.

- `pbHookFunction`

  \[out] указатель на значение, которое задается профилировщику для `true`, если требуется получить обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2`; в противном случае это значение задается как `false`.

## <a name="return-value"></a>Возвращаемое значение  
 Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции. Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`. В противном случае возвращаемое значение null приведет к непредсказуемым результатам, включая, возможно, остановку процесса.  
  
## <a name="remarks"></a>Заметки  
 Функция `FunctionIDMapper` является обратным вызовом. Он реализуется профилировщиком для повторного сопоставления идентификатора функции с другим идентификатором, который более удобен для профилировщика. `FunctionIDMapper` возвращает альтернативный идентификатор, используемый для любой заданной функции. Затем подсистема выполнения обрабатывает запрос профилировщика, передавая этот альтернативный идентификатор, помимо традиционного идентификатора функции, обратно в профилировщик в параметре `clientData` обработчиков `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для идентификации функции, для которой вызывается обработчик.  
  
 Для указания реализации функции `FunctionIDMapper` можно использовать метод [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) . Метод `ICorProfilerInfo::SetFunctionIDMapper` можно вызвать только один раз, и мы рекомендуем сделать это в обратном вызове [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .  
  
 По умолчанию предполагается, что профилировщик, устанавливающий флаг COR_PRF_MONITOR_ENTERLEAVE, с помощью [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md), который устанавливает перехватчики через [ICorProfilerInfo:: сетентерлеавефунктионхукс](icorprofilerinfo-setenterleavefunctionhooks-method.md) или [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должен получить обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для каждой функции. Однако профилировщики могут реализовать `FunctionIDMapper`, чтобы выборочно избежать получения этих обратных вызовов для определенных функций, установив для `pbHookFunction` значение `false`.  
  
 Профилировщики должны быть нечувствительными к случаям, когда несколько потоков профилированного приложения вызывают один и тот же метод или функцию одновременно. В таких случаях профилировщик может получить несколько `FunctionIDMapper`ных обратных вызовов для одного и того же `FunctionID`. Профилировщик должен быть уверенным в том, чтобы возвращать те же значения из этого обратного вызова, когда он вызывается несколько раз с одним и тем же `FunctionID`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Функция FunctionIDMapper2](functionidmapper2-function.md)
- [Функция FunctionEnter2](functionenter2-function.md)
- [Функция FunctionLeave2](functionleave2-function.md)
- [Функция FunctionTailcall2](functiontailcall2-function.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
