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
ms.openlocfilehash: ef2c518f8f3f3069e93f06de89add1385cb4e45e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445115"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>Метод ICorProfilerCallback::ClassLoadFinished
Уведомляет профилировщик о том, что загрузка класса завершена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 окне Идентифицирует загруженный класс.  
  
 `hrStatus`  
 окне Значение HRESULT, указывающее, успешно ли загружен класс.  
  
## <a name="remarks"></a>Заметки  
 Значение `classId` недопустимо для информационного запроса, пока не будет вызван метод `ClassLoadFinished`.  
  
 Некоторые части загрузки класса могут продолжаться после обратного вызова `ClassLoadFinished`. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть загрузки класса завершилась успешно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
