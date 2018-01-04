---
title: "Метод ICorProfilerInfo3::RequestProfilerDetach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.RequestProfilerDetach Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33a5c45bbb64029177a0a680243dd39a825683e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>Метод ICorProfilerInfo3::RequestProfilerDetach
Дает среде выполнения команду на отключение профилировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
#### <a name="parameters"></a>Параметры  
 `dwExpectedCompletionMilliseconds`  
 [in] Время в миллисекундах, которое должна ожидать среда CLR, прежде чем проверить, безопасно ли выгружать профилировщик.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Запрос отсоединения является допустимым, и процедура отсоединения теперь продолжается в другом потоке. После полного выполнения отсоединения выдается событие `ProfilerDetachSucceeded`.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|Сбой профилировщика [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) попытка выполнения [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) интерфейс, который должен быть реализован для поддержки операции отсоединения. Попытка отсоединения не выполнялась.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|Отсоединение невозможно, так как профилировщик установил неизменяемые флаги во время запуска. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Отсоединение невозможно, так как профилировщик использовал инструментированный код MSIL (MSIL) или вставил `enter` / `leave` обработчики. Попытка отсоединения не выполнялась; профилировщик по-прежнему полностью присоединен.<br /><br /> **Примечание** инструментированный код MSIL — это код, который предоставляется профилировщиком с помощью [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) метод.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Среда выполнения еще не была инициализирована в управляемом приложении. (То есть среда выполнения не была полностью загружена.) Этот код ошибки, которые могут быть возвращены, если отсоединение запрашивается в обратном вызове профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) метод.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` был вызван в неподдерживаемое время. Это происходит, если метод вызывается для управляемого потока, но не в [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) метода или в [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) метод, который не допускает сбор мусора. Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Примечания  
 При выполнении процедуры отсоединения поток отсоединения (поток, созданный специально для отсоединения профилировщика) периодически проверяет, все ли потоки вышли из кода профилировщика. Профилировщик должен предоставить оценку, как долго это должно происходить, с помощью параметра `dwExpectedCompletionMilliseconds`. В качестве этого значения рекомендуется использовать обычное время, которое профилировщик проводит внутри любого конкретного метода `ICorProfilerCallback*`; это значение не должно быть меньше половины максимального времени, которое профилировщик предполагает потратить.  
  
 Поток отсоединения использует `dwExpectedCompletionMilliseconds`, чтобы определить продолжительность бездействия перед проверкой, был ли код обратного вызова профилировщика удален из всех стеков. Хотя сведения о следующем алгоритме могут измениться в будущих выпусках среды CLR, он иллюстрирует один из способов `dwExpectedCompletionMilliseconds`, который можно использовать при определении того, когда можно безопасно выгрузить профилировщик. Поток отсоединения сначала находится в неактивном состоянии в течение `dwExpectedCompletionMilliseconds` миллисекунд. Если после выхода из спящего режима среда CLR обнаруживает, что код обратного вызова профилировщика все еще присутствует, поток отсоединения снова, бездействует в этот раз на удвоенное `dwExpectedCompletionMilliseconds` миллисекунд. Если после выхода из этого второго неактивного состояния поток отсоединения обнаруживает, что код обратного вызова профилировщика все еще присутствует, то он бездействует в течение 10 минут перед еще одной проверкой. Поток отсоединения продолжает выполнять очередную проверку каждые 10 минут.  
  
 Если профилировщик указывает `dwExpectedCompletionMilliseconds` как 0 (ноль), среда CLR использует значение по умолчанию 5000, которое означает, что проверка будет выполняться через 5 секунд, следующая проверка через 10 секунд, и затем каждые 10 минут соответственно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Профилирование](../../../../docs/framework/unmanaged-api/profiling/index.md)
