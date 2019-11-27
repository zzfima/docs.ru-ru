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
ms.openlocfilehash: 5d3fe6691a2d9989de002bad09c2e8f66a094f56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448432"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью генератора образов в машинном кодах (NGen. exe).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Параметры  
 `functionId`  
 окне Идентификатор функции, для которой выполняется поиск.  
  
 `pbUseCachedFunction`  
 [out] `true`, если подсистема выполнения должна использовать кэшированную версию функции (если она доступна); в противном случае `false`. Если значение равно `false`, подсистема выполнения JIT-компилирует функцию вместо использования версии, которая не является JIT-скомпилированной.  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 2,0 обратные вызовы методов `JITCachedFunctionSearchStarted` и [ICorProfilerCallback:: житкачедфунктионсеарчфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) не будут выполняться для всех функций в обычных образах Ngen. Только образы NGen, оптимизированные для профиля, будут создавать обратные вызовы для всех функций в образе. Однако из-за дополнительных издержек профилировщик должен запросить оптимизированные профилировщиком генераторы NGen только в том случае, если планируется использовать эти обратные вызовы для принудительной компиляции функции JIT (JIT). В противном случае профилировщик должен использовать отложенную стратегию для сбора сведений о функции.  
  
 Профилировщики должны поддерживать случаи, когда несколько потоков профилированного приложения одновременно вызывают один и тот же метод. Например, поток а вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, устанавливая для *пбусекачедфунктион*значение false для ПРИНУДИТЕЛЬной JIT-компиляции. Затем поток а вызывает метод [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Теперь поток B вызывает `JITCachedFunctionSearchStarted` для одной и той же функции. Несмотря на то, что профилировщик заявляет намерение выполнить JIT-компиляцию функции, профилировщик получает второй обратный вызов, так как поток B отправляет обратный вызов до того, как профилировщик ответит на вызов потока A в `JITCachedFunctionSearchStarted`. Порядок, в котором потоки выполняют вызовы, зависит от того, как запланированы потоки.  
  
 Когда профилировщик получает дублирующиеся обратные вызовы, он должен задать значение, на которое ссылается `pbUseCachedFunction`, на то же значение для всех повторяющихся обратных вызовов. То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с одним и тем же `functionId` значением, профилировщик должен каждый раз отвечать на эти же значения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
