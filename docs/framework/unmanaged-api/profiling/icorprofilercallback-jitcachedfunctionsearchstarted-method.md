---
title: "Метод ICorProfilerCallback::JITCachedFunctionSearchStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09fcdc67dc730b59b76a2da9f6ccea04800e20c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>Метод ICorProfilerCallback::JITCachedFunctionSearchStarted
Уведомляет профилировщик о начале поиска для функции, скомпилированной ранее с помощью генератором образов в машинном коде (NGen.exe).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a>Параметры  
 `functionId`  
 [in] Идентификатор функции, для которой выполняется поиск.  
  
 `pbUseCachedFunction`  
 [out] `true` Если ядро выполнения должен использовать кэшированная версия функции (если доступно); в противном случае `false`. Если значение равно `false`, ядро выполнения JIT-компиляцию функции, вместо того чтобы использовать версию, которая не является JIT-компиляции.  
  
## <a name="remarks"></a>Примечания  
 В .NET Framework версии 2.0 `JITCachedFunctionSearchStarted` и [метод ICorProfilerCallback::JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) обратные вызовы не будут совершаться для всех функций в обычных образов NGen. Образы NGen, оптимизированные под профиль создаст обратные вызовы для всех функций в образе. Однако из-за дополнительных служебных данных профилировщик должен запрашивать оптимизированные образы NGen, только в том случае, если он будет использовать эти обратные вызовы для принудительного функцией скомпилированных just-in-time (JIT). В противном случае профилировщик должен использовать пассивную стратегию для сбора сведений о функции.  
  
 Профилировщики должны поддерживать ситуации, когда несколько потоков профилируемого приложения вызывают тот же метод одновременно. Например, поток A вызывает `JITCachedFunctionSearchStarted` и профилировщик отвечает, устанавливая *pbUseCachedFunction*значение FALSE, чтобы принудительно JIT-компиляции. Затем вызывает потоком [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) и [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Теперь поток вызывает метод B `JITCachedFunctionSearchStarted` для той же функции. Несмотря на то, что профилировщик объявил его намерение JIT-компиляцию функции, профилировщик получает обратный вызов, поскольку поток B отправляет обратный вызов перед профилировщик ответил на вызов потоком `JITCachedFunctionSearchStarted`. Порядок, в котором потоки выполняют вызовы зависит от того, как они запланированы.  
  
 Когда профилировщик получает дублирующиеся обратные вызовы, его значение должно быть ссылается `pbUseCachedFunction` то же значение для всех обратных вызовов. То есть, когда `JITCachedFunctionSearchStarted` вызывается несколько раз с одинаковым `functionId` значение, профилировщик должен ответить же каждый раз.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
