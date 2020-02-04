---
title: Метод ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: 734ae1d14d02d47c7d3126f1b4cf55dcb4ad151b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866628"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>Метод ICorProfilerCallback::AssemblyUnloadFinished
Уведомляет профилировщик о том, что сборка была выгружена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Параметры

- `assemblyId`

  \[в] определяет сборку, которая выгружается.

- `hrStatus`

  \[in] значение HRESULT, указывающее, успешно ли выгружена сборка.

## <a name="remarks"></a>Заметки  
 Значение `assemblyId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: ассемблюнлоадстартед](icorprofilercallback-assemblyunloadstarted-method.md) .  
  
 Некоторые части выгрузки сборки могут продолжаться после обратного вызова `AssemblyUnloadFinished`. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть выгрузки сборки завершилась успешно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
