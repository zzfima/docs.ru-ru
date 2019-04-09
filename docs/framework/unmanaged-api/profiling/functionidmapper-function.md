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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2de19252b5c978fef38124636e4098ae5ece1b0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097942"
---
# <a name="functionidmapper-function"></a>Функция FunctionIDMapper
Уведомляет профилировщик о заданному идентификатору функции может быть альтернативный идентификатор для использования в [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), и [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) обратные вызовы для этой функции. `FunctionIDMapper` также позволяет профилировщику указать, желает ли он получать обратные вызовы для этой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcId`  
 [in] Идентификатор функции для повторного сопоставления.  
  
 `pbHookFunction`  
 [out] Указатель на значение, заданное профилировщиком `true` Если требуется получать `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` обратных вызовов; в противном случае это значение устанавливается равным `false`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Профилировщик возвращает значение, которое использует подсистема выполнения в качестве альтернативного идентификатора функции. Это возвращаемое значение не может быть значением null, если указатель `pbHookFunction` возвращает значение `false`. В противном случае возвращаемое значение null будет приводят к непредсказуемым результатам, включая возможное прерывание процесса.  
  
## <a name="remarks"></a>Примечания  
 `FunctionIDMapper` Функция является обратным вызовом. Она реализуется профилировщиком для повторного сопоставления идентификатора функции другой идентификатор, который лучше подходит для профилировщика. `FunctionIDMapper` Возвращает альтернативный идентификатор, который будет использоваться для любой заданной функции. Затем ядро выполнения выполняет запрос профилировщика, передав этот альтернативный идентификатор в дополнение к традиционному Идентификатору функции профилировщика в `clientData` параметр `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` ловушки, для идентификации функция, для которого вызывается обработчик.  
  
 Можно использовать [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) метод, чтобы задать реализацию `FunctionIDMapper` функции. Можно вызвать `ICorProfilerInfo::SetFunctionIDMapper` метод только один раз и мы рекомендуем, поэтому в выполнить [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) обратного вызова.  
  
 По умолчанию предполагается, что профилировщик, задает COR_PRF_MONITOR_ENTERLEAVE флаг с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), и который устанавливает обработчики через [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) или [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), должны получать `FunctionEnter2`, `FunctionLeave2`, и `FunctionTailcall2` обратных вызовов для каждой функции. Тем не менее, профилировщики могут реализовать `FunctionIDMapper` для выборочно избежать получения этих обратных вызовов для определенных функций, задав `pbHookFunction` для `false`.  
  
 Средства профилирования должны быть устойчивы к ситуации, где несколько потоков профилируемого приложения вызывают метод или функция с тем же одновременно. В таких случаях профилировщика может появиться несколько `FunctionIDMapper` обратные вызовы для того же `FunctionID`. Профилировщик должен не забудьте вернуть те значения из этого обратного вызова, когда он вызывается несколько раз с тем же `FunctionID`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [Функция FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)
- [Функция FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [Функция FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [Функция FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
