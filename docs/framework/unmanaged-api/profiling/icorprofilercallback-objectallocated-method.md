---
title: Метод ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 10a000fd98ad12dc39f8f8338485d6bb4093ee07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782984"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>Метод ICorProfilerCallback::ObjectAllocated
Уведомляет профилировщик о том, что для объекта выделена память в куче.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Параметры  
 `objectId`  
 [in] Идентификатор объекта, для которого была выделена память.  
  
 `classId`  
 [in] Идентификатор класса, из которых объект является экземпляром.  
  
## <a name="remarks"></a>Примечания  
 `ObjectedAllocated` Метод не вызывается для выделений памяти из стека или неуправляемой памяти. `classId` Параметр можно ссылаться на класс в управляемом коде, который еще не загружена. Профилировщик получит обратный вызов загрузки класса для этого класса сразу после `ObjectAllocated` обратного вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [Метод ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
