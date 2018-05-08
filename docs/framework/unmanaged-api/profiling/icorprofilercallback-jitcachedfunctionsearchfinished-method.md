---
title: Метод ICorProfilerCallback::JITCachedFunctionSearchFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89c7b0fe0f3ade3f57aa50b100bc9b4ecc904a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>Метод ICorProfilerCallback::JITCachedFunctionSearchFinished
Уведомляет профилировщик об окончании поиска для функции, скомпилированной ранее с помощью генератором образов в машинном коде (NGen.exe).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которого выполняется поиск.  
  
 `result`  
 [in] Значение [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) перечисления, указывающее на результат поиска.  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 2.0 [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) и `JITCachedFunctionSearchFinished` не будут совершаться обратные вызовы для всех функций в обычных образов NGen. Образы NGen, оптимизированные под Профилировщик создаст обратные вызовы для всех функций в образе. Однако из-за дополнительных служебных данных профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если он будет использовать эти обратные вызовы для принудительного функцией скомпилированных just-in-time (JIT). В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
