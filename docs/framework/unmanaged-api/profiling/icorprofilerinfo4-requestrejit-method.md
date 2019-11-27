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
|S_OK|Была предпринята попытка пометить все методы для перекомпиляции JIT. Профилировщик должен реализовать метод [ICorProfilerCallback4:: режитеррор](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md) , чтобы определить, какие методы были успешно отмечены для повторной компиляции JIT.|  
|CORPROF_E_CALLBACK4_REQUIRED|Чтобы этот вызов поддерживался, профилировщик должен реализовать интерфейс [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) .|  
|CORPROF_E_REJIT_NOT_ENABLED|Перекомпиляция JIT не была включена. Необходимо включить повторную компиляцию JIT-компилятора во время инициализации с помощью метода [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) , чтобы установить флаг `COR_PRF_ENABLE_REJIT`.|  
|E_INVALIDARG|`cFunctions` имеет значение 0, либо `moduleIds` или `methodIds` `NULL`.|  
|||  
|E_OUTOFMEMORY|Среде CLR не удалось выполнить запрос, поскольку не хватило памяти.|  
  
## <a name="remarks"></a>Примечания  
 Вызовите `RequestReJIT`, чтобы среда выполнения перекомпилировала указанный набор функций. Затем профилировщик кода может использовать интерфейс [икорпрофилерфунктионконтрол](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) для настройки кода, формируемого при повторной компиляции функций. Это не влияет на функции, выполняющиеся в текущий момент; только на будущие вызовы функций. Если любая из указанных функций уже подверглась перекомпиляции JIT ранее, то запрос перекомпиляции эквивалентен восстановлению исходного состояния и перекомпиляции этой функции. Для сохранения возможности восстановления исходного состояния, когда JIT-компилятор компилирует исходную версию функции, он рассматривает только исходные версии вызывающих ее объектов для встраиваемых решений. Когда JIT-компилятор перекомпилирует функцию, он рассматривает текущие версии (перекомпилированные или исходные) ее  вызывающих объектов для встраивания.  
  
 Профилировщик обычно вызывает `RequestReJIT` в ответ на ввод пользователя, запрашивающего инструментирование профилировщиком одного или нескольких методов. `RequestReJIT` обычно приостанавливает работу среды выполнения, чтобы выполнить некоторые из ее работы, и потенциально может запустить сборку мусора. Таким образом, профилировщик должен вызывать `RequestReJIT` из потока, созданного им ранее, а не из потока, созданного средой CLR, который в текущий момент выполняет обратный вызов профилировщика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
