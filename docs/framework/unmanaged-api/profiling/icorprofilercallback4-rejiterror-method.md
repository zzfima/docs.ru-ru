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
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430105"
---
# <a name="icorprofilercallback4rejiterror-method"></a>Метод ICorProfilerCallback4::ReJITError
Уведомляет профилировщик о том, что компилятор JIT обнаружил ошибку в процессе перекомпиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне `ModuleID`, в котором была выполнена попытка повторной компиляции с ошибкой.  
  
 `methodId`  
 окне `MethodDef` метода, для которого была выполнена попытка повторной компиляции.  
  
 `functionId`  
 окне Экземпляр функции, который перекомпилируется или помечен для повторной компиляции. Это значение может быть `NULL`, если ошибка возникла для каждого метода, а не для отдельных экземпляров (например, если профилировщик указал недопустимый токен метаданных для повторной компиляции метода).  
  
 `hrStatus`  
 окне Значение HRESULT, указывающее природу сбоя. Список значений см. в разделе Status HRESULTs.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значения, возвращаемые из этого обратного вызова, игнорируются.  
  
## <a name="status-hresults"></a>Значения HRESULT для состояния  
  
|Массив значений HRESULT для состояния|Описание|  
|--------------------------|-----------------|  
|E_INVALIDARG|Маркер `moduleID` или `methodDef` `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Модуль еще не полностью загружен или находится в процессе выгрузки.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Указанный модуль был динамически создан (например, с `Reflection.Emit`) и поэтому не поддерживается этим методом.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Экземпляр метода создается в собираемой сборке и поэтому не может быть перекомпилирован. Обратите внимание, что типы и функции, определенные в контексте без отражения (например, `List<MyCollectibleStruct>`), можно создать в собираемой сборке.|  
|E_OUTOFMEMORY|В среде CLR возникла нехватка памяти при попытке пометить указанный метод для повторной компиляции JIT.|  
|Прочее|Операционная система возвратила сбой за пределами среды CLR. Например, если системный вызов для изменения защиты доступа к странице памяти завершается ошибкой, отображается сообщение об ошибке операционной системы.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
