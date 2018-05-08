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
ms.openlocfilehash: c6a218b58ed2ab40505204768f7d6071dea6db5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2-interface"></a>Интерфейс ICorProfilerCallback2
Предоставляет методы, используемые средой CLR (CLR) для уведомления профилировщика кода при событиях, на которые подписан профилировщик. `ICorProfilerCallback2` Интерфейс является расширением [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) интерфейса. Таким образом предоставляются новые обратные вызовы, представленные в платформе .NET Framework версии 2.0.  
  
> [!NOTE]
>  Каждая реализация метода должны возвращать значение HRESULT со значением S_OK на успех или E_FAIL в случае ошибки. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемого каждой обратного вызова, за исключением [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Уведомляет профилировщик кода, что объект с методом завершения поставлен в очередь на поток метода завершения для выполнения его `Finalize` метод.|  
|[Метод GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Уведомляет профилировщик о сбора мусора и всех обратных вызовов, выданные для него.|  
|[Метод GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Уведомляет профилировщик кода о начале сборки мусора.|  
|[Метод HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Уведомляет профилировщик кода, что был создан дескриптор сборки мусора.|  
|[Метод HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Уведомляет профилировщик кода уничтожение дескриптор сборки мусора.|  
|[Метод RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Уведомляет профилировщик о корневых ссылках после сборки мусора. Этот метод является расширением [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) метод.|  
|[Метод SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, пережившие сборку мусора.|  
|[Метод ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Уведомляет профилировщик кода об изменении имени потока.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает метод в `ICorProfilerCallback` (или `ICorProfilerCallback2`) интерфейс для уведомления профилировщика, когда событие, на которую подписка профилировщика, происходит. Это основной интерфейс обратного вызова через который среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода необходимо реализовать методы `ICorProfilerCallback` интерфейса. .NET Framework 2.0 и более поздних версиях, профилировщик должен также реализовать `ICorProfilerCallback2` методы. Каждая реализация метода должны возвращать значение HRESULT со значением S_OK на успех или E_FAIL в случае ошибки. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемого каждой обратного вызова, за исключением [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Профилировщик кода необходимо зарегистрировать в реестре Microsoft Windows, COM-объекта, реализующего `ICorProfilerCallback` и `ICorProfilerCallback2` интерфейсов. Профилировщик кода подписывается на события, для которых требуется получать уведомления путем вызова [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Затем, профилировщик может получать уведомления из среды выполнения при возникновении события о или просто произошла в процессе среды выполнения.  
  
> [!NOTE]
>  Профилировщик регистрирует один COM-объектом. Если профилировщик предназначен для платформы .NET Framework версии 1.0 или 1.1, что COM-объекта требуется реализовать только методы `ICorProfilerCallback`. Если он предназначен для .NET Framework версии 2.0 и более поздней версии, COM-объекта, необходимо также реализовать методы `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Интерфейс ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [Интерфейс ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
