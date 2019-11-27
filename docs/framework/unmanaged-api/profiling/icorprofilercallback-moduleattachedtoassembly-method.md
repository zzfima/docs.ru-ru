---
title: Метод ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: d229b530062d759ab270612fa70b1799acbcadbe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448068"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>Метод ICorProfilerCallback::ModuleAttachedToAssembly
Уведомляет профилировщик о том, что модуль присоединен к своей родительской сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 окне Идентификатор присоединяемого модуля.  
  
 `AssemblyId`  
 окне ИДЕНТИФИКАТОР родительской сборки, к которой присоединен модуль.  
  
## <a name="remarks"></a>Примечания  
 Модуль можно загрузить через таблицу адресов импорта (IAT) с помощью вызова `LoadLibrary`или через ссылку на метаданные. В результате загрузчик среды CLR имеет несколько путей кода для определения сборки, в которой находится модуль. Таким образом, после вызова метода [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) модуль не знает, в какой сборке он находится, и получение идентификатора родительской сборки невозможно. Метод `ModuleAttachedToAssembly` вызывается, когда модуль присоединяется к своей родительской сборке и может быть получен идентификатор его родительской сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
