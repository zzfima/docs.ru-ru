---
title: Метод ICorProfilerInfo3::RequestProfilerDetach
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
ms.openlocfilehash: 3256f6f64e2ee4678b2627eea81e12cb4a02fd1e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449622"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>Метод ICorProfilerInfo3::RequestProfilerDetach
Дает среде выполнения команду на отключение профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwExpectedCompletionMilliseconds`  
 [in] Время в миллисекундах, которое должна ожидать среда CLR, прежде чем проверить, безопасно ли выгружать профилировщик.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Запрос отсоединения является допустимым, и процедура отсоединения теперь продолжается в другом потоке. После полного выполнения отсоединения выдается событие `ProfilerDetachSucceeded`.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|The profiler failed an [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) attempt for the [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) interface, which it must implement to support the detach operation. Попытка отсоединения не выполнялась.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Отсоединение невозможно, так как профилировщик установил неизменяемые флаги во время запуска. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Detachment is impossible because the profiler used instrumented Microsoft intermediate language (MSIL) code, or inserted `enter`/`leave` hooks. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.<br /><br /> **Note** Instrumented MSIL is code is code that is provided by the profiler using the [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Среда выполнения еще не была инициализирована в управляемом приложении. (That is, the runtime has not been fully loaded.) This error code may be returned when detachment is requested inside the profiler callback's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` был вызван в неподдерживаемое время. This occurs if the method is called on a managed thread but not from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method or from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method that cannot tolerate a garbage collection. For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Заметки  
 При выполнении процедуры отсоединения поток отсоединения (поток, созданный специально для отсоединения профилировщика) периодически проверяет, все ли потоки вышли из кода профилировщика. Профилировщик должен предоставить оценку, как долго это должно происходить, с помощью параметра `dwExpectedCompletionMilliseconds`. В качестве этого значения рекомендуется использовать обычное время, которое профилировщик проводит внутри любого конкретного метода `ICorProfilerCallback*`; это значение не должно быть меньше половины максимального времени, которое профилировщик предполагает потратить.  
  
 Поток отсоединения использует `dwExpectedCompletionMilliseconds`, чтобы определить продолжительность бездействия перед проверкой, был ли код обратного вызова профилировщика удален из всех стеков. Хотя сведения о следующем алгоритме могут измениться в будущих выпусках среды CLR, он иллюстрирует один из способов `dwExpectedCompletionMilliseconds`, который можно использовать при определении того, когда можно безопасно выгрузить профилировщик. Поток отсоединения сначала находится в неактивном состоянии в течение `dwExpectedCompletionMilliseconds` миллисекунд. If, after awakening from the sleep, the CLR finds that profiler callback code is still present, the detach thread sleeps again, this time for two times `dwExpectedCompletionMilliseconds` milliseconds. Если после выхода из этого второго неактивного состояния поток отсоединения обнаруживает, что код обратного вызова профилировщика все еще присутствует, то он бездействует в течение 10 минут перед еще одной проверкой. Поток отсоединения продолжает выполнять очередную проверку каждые 10 минут.  
  
 Если профилировщик указывает `dwExpectedCompletionMilliseconds` как 0 (ноль), среда CLR использует значение по умолчанию 5000, которое означает, что проверка будет выполняться через 5 секунд, следующая проверка через 10 секунд, и затем каждые 10 минут соответственно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
