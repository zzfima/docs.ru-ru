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
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867078"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>Перечисление COR_PRF_SUSPEND_REASON
Указывает причину приостановки выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Среда выполнения приостановлена для обслуживания запроса на сборку мусора.<br /><br /> Обратные вызовы, связанные со сборкой мусора, происходят между обратными вызовами [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) и [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Среда выполнения приостановлена, чтобы можно было завершить работу `AppDomain`.<br /><br /> Пока среда выполнения приостановлена, среда выполнения определит, какие потоки находятся в `AppDomain`, который завершает работу, и задайте для них значение Abort при возобновлении. Во время этой приостановки не `AppDomain`обратных вызовов.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Среда выполнения приостановлена, поэтому может произойти пошаговое выполнение кода.<br /><br /> Шаг с текстом выполняется, только если JIT-компилятор активен с включенным шагом в коде. Обратные вызовы с пошаговым выполнением кода происходят между `ICorProfilerCallback::RuntimeSuspendFinished` и `ICorProfilerCallback::RuntimeResumeStarted` обратными вызовами. **Примечание.**  JIT-компилятор CLR не выполняет функции в .NET Framework версии 2,0, поэтому это значение не используется в 2,0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Среда выполнения приостановлена, поэтому она может завершить работу. Чтобы завершить операцию, необходимо приостановить все потоки.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Среда выполнения приостанавливается для внутрипроцессного процесса отладки.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Среда выполнения приостановлена для подготовки к сбору мусора.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Среда выполнения приостанавливается для повторной компиляции JIT.|  
  
## <a name="remarks"></a>Заметки  
 Все потоки среды выполнения, наявляющиеся в неуправляемом коде, могут продолжать выполняться до тех пор, пока они не попытаются повторно войти в среду выполнения, после чего они также будут приостановлены до тех пор, пока среда выполнения не возобновит работу. Это также относится к новым потокам, которые вводят среду выполнения. Все потоки в среде выполнения либо приостанавливаются немедленно, если они находятся в коде для преобразования, либо запрашивается их приостановка, когда они достигают кода источника.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления профилирования](profiling-enumerations.md)
