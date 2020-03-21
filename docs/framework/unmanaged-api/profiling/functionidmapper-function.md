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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175178"
---
# <a name="functionidmapper-function"></a>Функция FunctionIDMapper
Уведомляет профайлер о том, что данный идентификатор функции может быть перенаправлен в альтернативный идентификатор, который будет использоваться в [FunctionEnter2,](functionenter2-function.md) [FunctionLeave2](functionleave2-function.md)и [FunctionTailcall2](functiontailcall2-function.md) для обратных вызовов для этой функции. `FunctionIDMapper` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Параметры

- `funcId`

  \[в» идентификатор функции, который будет remapped.

- `pbHookFunction`

  \[из указателя на значение, которое профайлер устанавливает, `true` если он хочет получить, `FunctionEnter2` `FunctionLeave2`, и `FunctionTailcall2` обратные вызовы; в противном случае, `false`он устанавливает это значение для .

## <a name="return-value"></a>Возвращаемое значение  
 Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции. Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`. В противном случае значение нулевой доходности приведет к непредсказуемым результатам, включая возможное прекращение процесса.  
  
## <a name="remarks"></a>Remarks  
 Функция `FunctionIDMapper` является обратным вызовом. Он реализован профайлером для переоценки идентификатора функции на другой идентификатор, который является более полезным для профайлера. Возвращает `FunctionIDMapper` альтернативный идентификатор, который будет использоваться для любой данной функции. Двигатель исполнения затем выполняет запрос профайлера, передавая этот альтернативный идентификатор, в `clientData` дополнение к `FunctionEnter2` `FunctionLeave2`традиционной `FunctionTailcall2` идентификатор функции, обратно к профилировщику в параметре , и крючки, чтобы определить функцию, для которой крючок вызывается.  
  
 Вы можете использовать метод [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) для `FunctionIDMapper` указания реализации функции. Вы можете `ICorProfilerInfo::SetFunctionIDMapper` позвонить по методу только один раз, и мы рекомендуем вам сделать это в [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) обратный вызов.  
  
 По умолчанию предполагается, что профайлер, который устанавливает COR_PRF_MONITOR_ENTERLEAVE флаг с помощью [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), и который устанавливает крючки через [ICorProfilerInfo::SetEnterLeaveFunctionХукс](icorprofilerinfo-setenterleavefunctionhooks-method.md) или `FunctionTailcall2` [ICorProfilerInfo2::SetEnterLeaveFunctionХикс2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должны получать `FunctionEnter2`, `FunctionLeave2`, и обратные вызовы для каждой функции. Тем не менее, `FunctionIDMapper` профайлеры могут осуществлять выборочно избегать получения этих обратных вызовов для определенных функций, установив `pbHookFunction` на `false`.  
  
 Профилеры должны быть терпимыми к случаям, когда несколько потоков профилированного приложения вызывают один и тот же метод/функцию одновременно. В таких случаях профайлер `FunctionIDMapper` может получить несколько `FunctionID`обратных вызовов за одно и то же . Профайлер должен быть уверен, чтобы вернуть те же значения из этого `FunctionID`обратного вызова, когда он называется несколько раз с тем же .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
- [Функция FunctionIDMapper2](functionidmapper2-function.md)
- [Функция FunctionEnter2](functionenter2-function.md)
- [Функция FunctionLeave2](functionleave2-function.md)
- [Функция FunctionTailcall2](functiontailcall2-function.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
