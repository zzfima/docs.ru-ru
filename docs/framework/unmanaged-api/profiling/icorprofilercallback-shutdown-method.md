---
title: Метод ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb2bfe927eddaf6812b0185a586135e76f649c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728126"
---
# <a name="icorprofilercallbackshutdown-method"></a>Метод ICorProfilerCallback::Shutdown
Уведомляет профилировщик, что приложение завершает работу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Примечания  
 Профилировщик кода не может безопасно вызывать методы из [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейс после `Shutdown` вызывается метод. Все вызовы `ICorProfilerInfo` метода приводят к неопределенному поведению после `Shutdown` возвращает метод. Некоторые неизменяемые события по-прежнему возникает после завершения работы; Профилировщик должен позаботиться о возвращать немедленно в том случае, когда это происходит.  
  
 `Shutdown` Метод будет вызываться только в том случае, если управляемое приложение, в которой производится профилирование запущен как управляемый код (то есть управляется начальный кадр в стеке процесса). Если приложение запущен как неуправляемый код, но позже осуществлен переход в управляемом коде, тем самым создавая экземпляра общеязыковой среды выполнения (CLR), затем `Shutdown` не будет вызван. В этих случаях профилировщик должен включать в собственной библиотеке `DllMain` подпрограмму, которая использует DLL_PROCESS_DETACH значение освободить все ресурсы и выполнить процесса очистки данных, например очистки трассировок на диске и т. д.  
  
 Как правило профилировщик должен быть рассчитан неожиданных выключений. Например, процесс может быть приостановлена из-за Win32 `TerminateProcess` метод (объявлен в Winbase.h). В других случаях CLR будет прерывать определенные управляемые потоки (фоновые потоки) без обеспечения надлежащих сообщений об удалении для них.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
