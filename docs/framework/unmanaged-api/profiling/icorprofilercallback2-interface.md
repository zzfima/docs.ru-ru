---
title: Интерфейс ICorProfilerCallback2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d36d8ef3bfdbd6a1acf787a91003e2ff3139a4d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963969"
---
# <a name="icorprofilercallback2-interface"></a>Интерфейс ICorProfilerCallback2
Предоставляет методы, используемые общеязыковой средой выполнения (CLR) для уведомления профилировщика кода о событиях, на которые подписан профилировщик. Интерфейс является расширением интерфейса [ICorProfilerCallback.](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) `ICorProfilerCallback2` То есть он предоставляет новые обратные вызовы, представленные в .NET Framework версии 2,0.  
  
> [!NOTE]
> Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успешного выполнения или E_FAIL в случае сбоя. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Уведомляет профилировщик кода о том, что объект с методом завершения был помещен в очередь в поток метода завершения для выполнения своего `Finalize` метода.|  
|[Метод GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Уведомляет профилировщик о завершении сборки мусора и выдачи всех обратных вызовов сборки мусора.|  
|[Метод GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Уведомляет профилировщик кода о начале сборки мусора.|  
|[Метод HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Уведомляет профилировщик кода о создании обработчика сборки мусора.|  
|[Метод HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Уведомляет профилировщик кода о том, что был уничтожен обработчик сборки мусора.|  
|[Метод RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением метода [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) .|  
|[Метод SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, которые были сохранившиются при сборке мусора.|  
|[Метод ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Уведомляет профилировщик кода о том, что имя потока изменилось.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает метод в `ICorProfilerCallback` интерфейсе (или `ICorProfilerCallback2`) для уведомления профилировщика при возникновении события, на которое подписан профилировщик. Это основной интерфейс обратного вызова, через который среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода должен реализовывать методы `ICorProfilerCallback` интерфейса. Для .NET Framework 2,0 и более поздних версий профилировщик также должен реализовать `ICorProfilerCallback2` методы. Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успешного выполнения или E_FAIL в случае сбоя. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Профилировщик кода должен быть зарегистрирован в реестре Microsoft Windows, его COM-объекте, который реализует `ICorProfilerCallback` интерфейсы и. `ICorProfilerCallback2` Профилировщик кода подписывается на события, для которых требуется получать уведомления, путем вызова [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации профилировщиком [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Затем профилировщик может получать уведомления от среды выполнения, когда в процессе в среде выполнения происходит или скоро произойдет событие.  
  
> [!NOTE]
> Профилировщик регистрирует один COM-объект. Если профилировщик предназначен для .NET Framework версии 1,0 или 1,1, этот COM-объект должен реализовывать только методы `ICorProfilerCallback`. Если он предназначен для `ICorProfilerCallback2`.NET Framework версии 2,0 и более поздних, то COM-объект также должен реализовывать методы.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf. idl, CorProf. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
