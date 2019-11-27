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
ms.openlocfilehash: 23c6f0a29160b6e1dc194cf360c07374c565522b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440706"
---
# <a name="functionidmapper-function"></a>Функция FunctionIDMapper
Уведомляет профилировщик о том, что заданный идентификатор функции может быть повторно сопоставлен с альтернативным ИДЕНТИФИКАТОРом для использования в обратных вызовах [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) для этой функции. `FunctionIDMapper` также позволяет профилировщику указывать, хотят ли они получать обратные вызовы для этой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcId`  
 [in] Идентификатор функции для повторного сопоставления.  
  
 `pbHookFunction`  
 заполняет Указатель на значение, которое задается профилировщику для `true`, если требуется получать обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2`; в противном случае это значение задается как `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции. Это возвращаемое значение не может быть значением null, если указатель `false` возвращает значение `pbHookFunction`. В противном случае возвращаемое значение null приведет к непредсказуемым результатам, включая, возможно, остановку процесса.  
  
## <a name="remarks"></a>Заметки  
 Функция `FunctionIDMapper` является обратным вызовом. Он реализуется профилировщиком для повторного сопоставления идентификатора функции с другим идентификатором, который более удобен для профилировщика. `FunctionIDMapper` возвращает альтернативный идентификатор, используемый для любой заданной функции. Затем подсистема выполнения обрабатывает запрос профилировщика, передавая этот альтернативный идентификатор, помимо традиционного идентификатора функции, обратно в профилировщик в параметре `clientData` обработчиков `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для идентификации функции, для которой вызывается обработчик.  
  
 Для указания реализации функции `FunctionIDMapper` можно использовать метод [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) . Метод `ICorProfilerInfo::SetFunctionIDMapper` можно вызвать только один раз, и мы рекомендуем сделать это в обратном вызове [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) .  
  
 По умолчанию предполагается, что профилировщик, устанавливающий флаг COR_PRF_MONITOR_ENTERLEAVE, с помощью [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), который устанавливает перехватчики через [ICorProfilerInfo:: сетентерлеавефунктионхукс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) или [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должен получить обратные вызовы `FunctionEnter2`, `FunctionLeave2`и `FunctionTailcall2` для каждой функции. Однако профилировщики могут реализовать `FunctionIDMapper`, чтобы выборочно избежать получения этих обратных вызовов для определенных функций, установив для `pbHookFunction` значение `false`.  
  
 Профилировщики должны быть нечувствительными к случаям, когда несколько потоков профилированного приложения вызывают один и тот же метод или функцию одновременно. В таких случаях профилировщик может получить несколько `FunctionIDMapper`ных обратных вызовов для одного и того же `FunctionID`. Профилировщик должен быть уверенным в том, чтобы возвращать те же значения из этого обратного вызова, когда он вызывается несколько раз с одним и тем же `FunctionID`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [Функция FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
