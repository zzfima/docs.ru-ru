---
title: Метод ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4c45290b1ef4360e51b5ed8e1b0fac3dcdde727
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041630"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a>Метод ICorProfilerCallback::ThreadDestroyed
Уведомляет профилировщик, что поток был удален.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadId`  
 [in] Идентификатор потока, который был удален.  
  
## <a name="remarks"></a>Примечания  
 `threadId` Значение больше не является допустимым во время этого вызова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
