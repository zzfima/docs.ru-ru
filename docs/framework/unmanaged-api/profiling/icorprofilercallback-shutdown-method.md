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
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446941"
---
# <a name="icorprofilercallbackshutdown-method"></a>Метод ICorProfilerCallback::Shutdown
Уведомляет профилировщик о том, что приложение завершает работу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Примечания  
 Код профилировщика не может безопасно вызывать методы интерфейса [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) после вызова метода `Shutdown`. Любые вызовы `ICorProfilerInfo` методов приводят к неопределенному поведению после возврата метода `Shutdown`. Некоторые неизменяемые события по-прежнему могут возникать после завершения работы. Профилировщик должен немедленно возвращаться к моменту, когда это происходит.  
  
 Метод `Shutdown` будет вызываться только в том случае, если управляемое приложение, профилирование которого запускается в качестве управляемого кода (то есть исходный кадр в стеке процессов является управляемым). Если приложение запущено как неуправляемый код, но позднее перейдем к управляемому коду, то, таким образом, создает экземпляр среды CLR, то `Shutdown` не будет вызываться. В таких случаях профилировщик должен включать в свою библиотеку `DllMain` подпрограммы, которая использует значение DLL_PROCESS_DETACH для высвобождения любых ресурсов и выполнения очистки данных, таких как сброс трассировок на диск и т. д.  
  
 Как правило, профилировщик должен справляться с непредвиденным завершением работы. Например, процесс может быть остановлен методом Win32's `TerminateProcess` (объявлен в Винбасе. h). В других случаях среда CLR остановит определенные управляемые потоки (фоновые потоки), не создавая для них сообщения с неупорядоченным уничтожением.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Метод Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
