---
title: "Метод ICorProfilerCallback::Shutdown"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a>Метод ICorProfilerCallback::Shutdown
Уведомляет профилировщик о том, что приложение завершает работу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Примечания  
 Профилировщик кода не может безопасно вызывать методы [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейса после `Shutdown` вызывается метод. Все вызовы `ICorProfilerInfo` метода приводят к неопределенному поведению после `Shutdown` возвращает метод. Некоторые неизменяемые события могут происходить после завершения работы; Профилировщик следует позаботиться о возвращают немедленно в том случае, когда это происходит.  
  
 `Shutdown` Метод будет вызываться только в том случае, если управляемого приложения, для которой производится профилирование запущен как управляемый код (то есть управляется начальный кадр в стеке процесса). Если приложение запущен как неуправляемый код, но позже осуществлен переход в управляемом коде, создавая экземпляр среды common language runtime (CLR), затем `Shutdown` не будет вызван. В этих случаях профилировщик должен включить в собственной библиотеке `DllMain` подпрограмму, которая использует DLL_PROCESS_DETACH значение освободить все ресурсы и выполнить процесса очистки данных, например очистки трассировок на диске и т. д.  
  
 Как правило профилировщик должен быть рассчитан неожиданных выключений. Например, процесс может быть прервана Win32 `TerminateProcess` метод (объявлено в Winbase.h). В других случаях CLR будет прерывать определенные управляемые потоки (фоновые потоки) без предоставления надлежащих сообщений об удалении для них.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Метод Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
