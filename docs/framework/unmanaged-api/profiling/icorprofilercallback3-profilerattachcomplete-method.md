---
title: Метод ICorProfilerCallback3::ProfilerAttachComplete
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: 4c5b8f18424ba54d9e8e14ba0a518a89e0d54796
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439462"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>Метод ICorProfilerCallback3::ProfilerAttachComplete
Вызывается средой CLR для указания на то, что профилировщик теперь может вызывать методы перехвата [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) и [ICorProfilerInfo3:: EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>Заметки  
 После вызова метода [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) выдается обратный вызов `ProfilerAttachComplete`. Он указывает следующее.  
  
- Обратные вызовы, которые были запрошены профилировщиком в `InitializeForAttach`, были активированы.  
  
- Профилировщик теперь может выполнять захват в связанных идентификаторах, не заботясь об отсутствующих уведомлениях.  
  
 Среда CLR игнорирует возвращаемое значение из этого обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
