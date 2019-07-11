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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3345e2e87ba41f750031deed2d15e13dbe4f06c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769291"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>Метод ICorProfilerCallback::ModuleAttachedToAssembly
Уведомляет профилировщик, что модуль присоединяется к ее родительской сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, который присоединяется.  
  
 `AssemblyId`  
 [in] Идентификатор родительской сборки, к которой подключен модуль.  
  
## <a name="remarks"></a>Примечания  
 Модуль может быть загружен посредством таблицы адресов импорта (IAT), посредством вызова `LoadLibrary`, или с помощью ссылки на метаданные. Таким образом загрузчик распространенных языковой среды выполнения (CLR) имеет несколько путей кода для определения сборки, в котором находится модуль. Таким образом, возможна после того как [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) вызывается, модуль не знает, какие сборки в и получение идентификатора родительской сборки не поддерживается. `ModuleAttachedToAssembly` При присоединении к ее родительской сборки и ее родительской сборки, можно получить идентификатор модуля, вызывается метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
