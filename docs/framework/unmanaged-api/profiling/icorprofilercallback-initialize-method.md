---
title: "Метод ICorProfilerCallback::Initialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Initialize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2eebe596b3459d51afe66df4bb81f74e93f3526e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackinitialize-method"></a>Метод ICorProfilerCallback::Initialize
Вызывается для инициализации профилировщика кода при запуске нового приложения среды CLR (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pICorProfilerInfoUnk`  
 [в](/cpp/atl/iunknown) интерфейс, профилировщик должен запрашивать [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) указатель на интерфейс.  
  
## <a name="remarks"></a>Примечания  
 `Initialize` Вызов является единственная возможность включить (или отключить) обратные вызовы, которые являются неизменяемыми. После включения обратный вызов по `Initialize` вызвать, его нельзя отключить позже с помощью [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Значение COR_PRF_MONITOR_IMMUTABLE [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления указывает, какие события являются неизменяемыми.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Shutdown-метод](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
