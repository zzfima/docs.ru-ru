---
title: Перечисление COR_PRF_SUSPEND_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f4382c7fa85008de9e67ad21c467402bae4ac90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corprfsuspendreason-enumeration"></a>Перечисление COR_PRF_SUSPEND_REASON
Указывает причину приостановки среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Среда выполнения приостановлена по неизвестной причине.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Среда выполнения приостановлена для обслуживания запросов на сбор мусора.<br /><br /> Коллекция связанных с обратные вызовы сборки мусора пройти между [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) и [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) обратные вызовы.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Среда выполнения приостановлена, чтобы `AppDomain` можно завершить работу.<br /><br /> Приостановленная среда выполнения, среда выполнения определяет потоки в `AppDomain` именно выполняется завершение работы и задайте их выполнения, когда они снова. Существуют не `AppDomain`-конкретных обратных вызовов во время этой приостановки.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Среда выполнения приостановлена, чтобы возможности пошагового выполнения.<br /><br /> Пошаговое выполнение кода гарантируется только когда компилятор just-in-time (JIT) активна с пошагового выполнения кода включено. Разделять обратные вызовы, пошагового выполнения кода `ICorProfilerCallback::RuntimeSuspendFinished` и `ICorProfilerCallback::RuntimeResumeStarted` обратные вызовы. **Примечание:** CLR JIT не пошаговое выполнение функций в платформе .NET Framework версии 2.0, поэтому это значение не используется в версии 2.0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Среда выполнения приостановлена, чтобы завершить работу. Его необходимо приостановить все потоки для завершения операции.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Среда выполнения приостановлена в процессе отладки.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Среда выполнения приостановлена для подготовки для сборки мусора.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Среда выполнения приостановлена для перекомпиляции JIT.|  
  
## <a name="remarks"></a>Примечания  
 Все потоки среды выполнения, которые находятся в неуправляемом коде могут продолжать выполняться, пока они пытаются заново ввести среды выполнения, после чего они также будут приостановлены среду выполнения. Это справедливо и для новых потоков, выполняющих вход в среду выполнения. Все потоки в среде выполнения либо приостановлен немедленно, если они находятся в коде, прерываемых запрос на приостановку по достижении такого кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
