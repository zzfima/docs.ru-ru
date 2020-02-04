---
title: Метод ICorProfilerCallback::AssemblyLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: b83be5e79c533e7e5a2468a12a0793d300700428
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866645"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a>Метод ICorProfilerCallback::AssemblyLoadStarted
Уведомляет профилировщик о загрузке сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a>Параметры

- `assemblyId`

  \[в] определяет загружаемую сборку.

## <a name="remarks"></a>Заметки  
 Значение `assemblyId` недопустимо для информационного запроса, пока не вызван метод [ICorProfilerCallback:: AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
