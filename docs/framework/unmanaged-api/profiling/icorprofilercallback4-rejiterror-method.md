---
title: "Метод ICorProfilerCallback4::ReJITError"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITError
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a>Метод ICorProfilerCallback4::ReJITError
Уведомляет профилировщик, что компилятор just-in-time (JIT) произошла ошибка в процессе повторной компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleID`  
 [in] `ModuleID` В которой была предпринята попытка сбой повторной компиляции.  
  
 `methodId`  
 [in] `MethodDef` Метода, в которой была предпринята попытка сбой повторной компиляции.  
  
 `functionId`  
 [in] Экземпляр функции, для которого создается перекомпилированные или отмечено для повторной компиляции. Это значение может быть `NULL` Если ошибка для каждого метода в отдельности вместо отдельно для каждого экземпляра (например, если профилировщик указанный маркер недопустимые метаданные для повторной компиляции метода).  
  
 `hrStatus`  
 [in] Значение HRESULT, указывающее причину сбоя. В разделе значения HRESULT для состояния список значений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значения, возвращаемые из этого обратного вызова, игнорируются.  
  
## <a name="status-hresults"></a>Значения HRESULT для состояния  
  
|Массив значений HRESULT для состояния|Описание:|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID` Или `methodDef` маркер `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Модуль еще не полностью загружен или находится в процессе выгрузки.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Указанный модуль был создан динамически (например, с `Reflection.Emit`) и поэтому не поддерживается этим методом.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Метод создается в собираемой сборке и таким образом, не может быть перекомпилирован. Обратите внимание, что типы и функции, определенные в контексте, отличном от отражения (например, `List<MyCollectibleStruct>`) могут быть созданы в собираемая сборка.|  
|E_OUTOFMEMORY|Среда CLR не хватило памяти при попытке пометить указанный метод для перекомпиляции JIT.|  
|Другое|Операционная система возвратила сбой за пределами среды CLR. Например сбой системного вызова изменения защиты доступа к странице памяти отображается ошибка операционной системы.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
