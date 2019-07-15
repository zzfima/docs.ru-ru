---
title: Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4d35179b8ae35c03370cc3798609d6ed430cde3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782852"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
Уведомляет профилировщик о начале поиска для функции, который был скомпилирован с помощью генератором машинных образов (NGen.exe).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которой выполняется поиск.  
  
 `pbUseCachedFunction`  
 [out] `true` Если ядро выполнения следует использовать кэшированную версию функции, (при наличии); в противном случае `false`. Если значение равно `false`, ядро выполнения JIT-компиляцию функции, вместо того чтобы использовать версию, которая не является JIT-компиляции.  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 2.0 `JITCachedFunctionSearchStarted` и [метод ICorProfilerCallback::JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) обратные вызовы не будут совершаться для всех функций в обычных образов NGen. Только образы NGen, оптимизированные для профиля будут создавать обратные вызовы для всех функций в образе. Тем не менее из-за дополнительных издержек, профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если планируется использовать эти обратные вызовы для принудительного функции скомпилированного just-in-time (JIT). В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.  
  
 Профилировщики должны поддерживать ситуации, где несколько потоков профилируемого приложения вызывают тот же метод одновременно. Например, поток A вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, задав *pbUseCachedFunction*значение false, чтобы принудительно JIT-компиляции. Поток, затем вызывает [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Теперь поток B вызывает `JITCachedFunctionSearchStarted` для той же функции. Несмотря на то, что профилировщик заявила о своем намерении выполнить JIT-компиляцию функции, профилировщик получает обратный вызов, так как поток B отправляет обратный вызов, прежде чем профилировщик ответил на вызов потока A `JITCachedFunctionSearchStarted`. Порядок, в котором потоки выполняют вызовы зависит от того, как запланировано потоков.  
  
 Когда профилировщик получает обратных вызовов, его необходимо задать значение ссылается `pbUseCachedFunction` то же значение для всех обратных вызовов. То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с тем же `functionId` значение, профилировщик должен вернуть же каждый раз.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
