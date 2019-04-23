---
title: Метод ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f152279a21f28b54acebbf0be7c65bb73efa70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150596"
---
# <a name="icorprofilercallback4rejiterror-method"></a>Метод ICorProfilerCallback4::ReJITError
Уведомляет профилировщик о том, что компилятор just-in-time (JIT) произошла ошибка в процессе повторной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 [in] `ModuleID` В которой была сделана попытка сбой повторной компиляции.  
  
 `methodId`  
 [in] `MethodDef` Метода, на котором была сделана попытка сбой повторной компиляции.  
  
 `functionId`  
 [in] Экземпляр функции, для которого выполняется повторная сборка или помечены для повторной компиляции. Это значение может быть `NULL` Если произошел на каждого метода вместо конкретных экземпляров (например, если профилировщик указан маркер недопустимые метаданные для метода повторной компиляции).  
  
 `hrStatus`  
 [in] Значение HRESULT, указывающее характер ошибки. См. в разделе значения HRESULT для состояния списка значений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значения, возвращаемые из этого обратного вызова, игнорируются.  
  
## <a name="status-hresults"></a>Значения HRESULT для состояния  
  
|Массив значений HRESULT для состояния|Описание|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID` Или `methodDef` маркер является `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Модуль еще не полностью загружен или находится в процессе выгрузки.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Указанный модуль был создан динамически (например, с `Reflection.Emit`) и поэтому не поддерживается этим методом.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Метод создается в забираемой сборке и поэтому не может быть перекомпилирован. Обратите внимание, что типы и функции, определенные в контексте, отличных от отражения (например, `List<MyCollectibleStruct>`) могут быть созданы в забираемой сборке.|  
|E_OUTOFMEMORY|Среда CLR не хватило памяти при попытке пометить указанный метод для перекомпиляции JIT.|  
|Другое|Операционная система возвратила сбой за пределами среды CLR. Например если происходит сбой системного вызова изменения защиты доступа к странице памяти, отображается ошибка операционной системы.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
