---
title: Метод ICorProfilerCallback::AssemblyLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866654"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>Метод ICorProfilerCallback::AssemblyLoadFinished
Уведомляет профилировщик о том, что загрузка сборки завершена.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Параметры

- `assemblyId`

  \[в] определяет сборку, которая была загружена.

- `hrStatus`

  \[in] значение HRESULT, указывающее, успешно ли завершена загрузка сборки.

## <a name="remarks"></a>Заметки  
 Значение `assemblyId` недопустимо для информационного запроса, пока не будет вызван метод `AssemblyLoadFinished`.  
  
 Некоторые части загрузки сборки могут продолжаться после обратного вызова `AssemblyLoadFinished`. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT успешного выполнения в `hrStatus` указывает только на то, что первая часть загрузки сборки завершилась успешно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
