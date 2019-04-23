---
title: Метод ICorProfilerCallback::ClassLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cab4b039d225f4ee1b00add6ffec63fd35be8857
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202811"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>Метод ICorProfilerCallback::ClassLoadFinished
Уведомляет профилировщик об окончании загрузки класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 [in] Идентифицирует класс, который был загружен.  
  
 `hrStatus`  
 [in] Значение HRESULT, указывающее, успешно ли загружен класс.  
  
## <a name="remarks"></a>Примечания  
 Значение `classId` не является допустимым для информационного запроса до `ClassLoadFinished` вызывается метод.  
  
 Загрузка класса некоторых частей может по-прежнему после `ClassLoadFinished` обратного вызова. Значение HRESULT в `hrStatus` указывает на сбой. Тем не менее значение HRESULT в `hrStatus` указывает, что первая часть загрузки класса выполнено успешно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
