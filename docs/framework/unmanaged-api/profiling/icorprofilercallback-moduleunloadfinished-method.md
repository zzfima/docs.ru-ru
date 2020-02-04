---
title: Метод ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
ms.openlocfilehash: b13573d19ab4d8bb655c1e153530dc70173abe82
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866147"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>Метод ICorProfilerCallback::ModuleUnloadFinished
Уведомляет профилировщик о завершении выгрузки модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор выгруженного модуля.  
  
 `hrStatus`  
 окне Значение HRESULT, указывающее, успешно ли выгружен модуль.  
  
## <a name="remarks"></a>Заметки  
 Значение `moduleId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) .  
  
 Некоторые части выгрузки класса могут продолжаться после обратного вызова `ModuleUnloadFinished`. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть выгрузки модуля успешно выполнена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
