---
title: Метод ICorProfilerInfo4::RequestReJIT
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: eb4d5e1c4efd67914df95868b67ec5cc3fe6139a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444822"
---
# <a name="icorprofilerinfo4requestrejit-method"></a>Метод ICorProfilerInfo4::RequestReJIT
Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a>Параметры  
 `cFunctions`  
 [in] Число функций для перекомпиляции.  
  
 `moduleIds`  
 [in] Указывает часть `moduleId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.  
  
 `methodIds`  
 [in] Указывает часть `methodId` пар (`module`, `methodDef`), которые идентифицируют перекомпилируемые функции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Была предпринята попытка пометить все методы для перекомпиляции JIT. The profiler must implement the [ICorProfilerCallback4::ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.|  
|CORPROF_E_CALLBACK4_REQUIRED|The profiler must implement the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface for this call to be supported.|  
|CORPROF_E_REJIT_NOT_ENABLED|Перекомпиляция JIT не была включена. You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.|  
|E_INVALIDARG|Параметр `cFunctions` имеет значение 0, либо один из параметров `moduleIds` и `methodIds` имеет значение `NULL`.|  
|||  
|E_OUTOFMEMORY|Среде CLR не удалось выполнить запрос, поскольку не хватило памяти.|  
  
## <a name="remarks"></a>Заметки  
 Вызовите `RequestReJIT`, чтобы среда выполнения перекомпилировала указанный набор функций. A code profiler can then use the [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled. Это не влияет на функции, выполняющиеся в текущий момент; только на будущие вызовы функций. Если любая из указанных функций уже подверглась перекомпиляции JIT ранее, то запрос перекомпиляции эквивалентен восстановлению исходного состояния и перекомпиляции этой функции. Для сохранения возможности восстановления исходного состояния, когда JIT-компилятор компилирует исходную версию функции, он рассматривает только исходные версии вызывающих ее объектов для встраиваемых решений. Когда JIT-компилятор перекомпилирует функцию, он рассматривает текущие версии (перекомпилированные или исходные) ее  вызывающих объектов для встраивания.  
  
 Профилировщик обычно вызывает `RequestReJIT` в ответ на ввод пользователя, запрашивающего инструментирование профилировщиком одного или нескольких методов. Обычно `RequestReJIT` приостанавливает среду выполнения для выполнения некоторых операций и потенциально может инициировать сборку мусора. Таким образом, профилировщик должен вызывать `RequestReJIT` из потока, созданного им ранее, а не из потока, созданного средой CLR, который в текущий момент выполняет обратный вызов профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
